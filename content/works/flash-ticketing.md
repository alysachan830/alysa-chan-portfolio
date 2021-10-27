---
title: Flash Ticketing
year: 2021
coverImg: /images/flash_ticketing_mockup.jpg
url: https://flash-ticketing.com/
role: Front-end development, UI/UX design
technologies: Nuxt.js, Adobe XD
description: Flash ticketing is a personal project which imitates an online ticketing platform for art and cultural events during my study in an online Vue.js bootcamp. I worked on the UI/UX design and front-end with Nuxt.js, for developing a server-side rendering (SSR) website. The goal is to enhance my front-end development skills with Nuxt.js and understand how an online e-commerce or ticketing platform works basically.
---

<section class="mb-20 d-flex justify-content-center">
    <img src="/images/flash_ticketing_video.gif">
</section>

<section class="mb-20">

## Features

**Ticketing platform**

- Show all events in different categories, with different types, zone seating, event dates of tickets
- Add, edit or delete items in shopping cart and my favourite list
- Form validation in order form with Vee-validate
- Apply coupon with coupon code
- Add an order to server after user finishes his purchase

**Admin dashboard**

- Login and logout feature with token-based authentication
- Add, edit or delete events, orders and coupons

**Deployment**

- Automatic deployment on Vercel with a GitHub branch

**Image optimization**

- Use Cloudinary for optimizing images fetched from API

</section>

<section>

## Event details and tickets

<image-wrap :images="[
{url: '/images/flash_ticketing_event_detail.jpg'}, 
{url: '/images/flash_ticketing_event_all_tickets.jpg'}
]">
</image-wrap>

<image-wrap :images="[
{url: '/images/flash_ticketing_purchase.jpg'}, 
{url: '/images/flash_ticketing_form.jpg'}
]">
</image-wrap>

</section>

<section>

## Responsive design

<image-wrap :images="[
{url: '/images/mobile_flash_ticketing_homepage.jpg'}, 
{url: '/images/mobile_flash_ticketing_event_detail.jpg'}, 
{url: '/images/mobile_flash_ticketing_purchase.png'}
]" :is-responsive="false">
</image-wrap>

</section>

<section>

## Admin dashboard

<image-wrap :images="[
{url: '/images/flash_ticketing_dashboard_show_event.jpg'}, 
{url: '/images/flash_ticketing_dashboard_edit_event.jpg'}
]">
</image-wrap>

</section>

<section>

## Challenges

**The APIs are not designed for ticketing platform**

Since my online bootcamp is an introductory course of building a basic e-commerce website with Vue.js, the APIs are not designed for ticketing website. They are basic CRUD products with fixed prices and simple product details.

<span class="text-primary">

[→ APIs provided by the bootcamp](https://github.com/hexschool/vue3-course-api-wiki/wiki)

</span>

However, in my case, I have different events with different ticket types and seating zones. The challenge for me was how to create different ticket types with different prices of a single event.

**Two major problems I had to solve:**

1. How to store the quantity of different tickets of a single event in the shopping cart?
2. How to calculate the total amount of the shopping cart correctly?

</section>

<section>

<section>

## Challenge 1

**Store quantity of different types of tickets in a single event**

<section class="mb-20">

When I add a specific ticket type of an event to the cart, the simplest way is to call the add to cart API `[POST]` and add a custom property to in an event item in the cart.

Yet, this is not a workable solution because:

- Value of the custom property will not be accelerated
- Value of the custom property will be overwritten if I send the request with data that has the same product id

</section>

<section class="mb-18">

For example, here is a data of an event, "夏日序曲 — 莫扎特的交響樂" :

```json
{
        "category": "音樂",
        "dateTime": [
            {
                "date": "2021-08-11",
                "endTime": "13:30",
                "startTime": "12:00",
                "timestamp": 1625891831522
            },
            ...
        ],
        "id": "-MeDhhevaeV5e8wUDUuS",
        "ticketPrice": {
            "A": 240,
            "B": 360,
            "C": 420
        },
        "title": "夏日序曲 — 莫扎特的交響樂",
        ...
},
```

</section>

<section class="mb-18">

Here is the data of the cart after a user adds a specific ticket type to the cart:

```json
"carts": [
    {
        "1625891831522,A區,正價票": 1,
        "id": "-Mn-feaX5aMbyXZUrHrs",
        "product": {
            "title": "夏日序曲 — 莫扎特的交響樂",
            ...
        },
        "product_id": "-MeDhhevaeV5e8wUDUuS",
        ...
    }
]
```

</section>

<section class="mb-18">

If user adds one more `1625891831522,A區,正價票 ticket`, the value of `1625891831522,A區,正價票` will still be 1 instead of 2, because it overwrites the previous data:

```json
"carts": [
    {
        "1625891831522,A區,正價票": 1,
        ...
    }
]
```

</section>

<section class="mb-18">

Same problem occurs if the user adds a different ticket type.

For example, if the user adds `1625891831522,C區,優惠票`, then `1625891831522,A區,正價票` will be overwritten. Here is the result:

```json
"carts": [
    {
        "1625891831522,C區,優惠票": 1,
        "id": "-Mn-feaX5aMbyXZUrHrs",
        "product": {
            "title": "夏日序曲 — 莫扎特的交響樂",
            ...
        },
        "product_id": "-MeDhhevaeV5e8wUDUuS",
        ...
    }
]
```

</section>

</section>

<section>

## Solution

<section class="mb-18">

**Call edit cart API if I have to accumulate the quantity**

Since I was using the API developed by the bootcamp, changing the APIs was not an option for me and I had to solve it in front-end. To avoid overwriting the current data when I had to accumulate the quantity, I would call edit cart `PUT` API. Below is my algorithm for solving this problem.

</section>

<section>

<section class="mb-18">

**Algorithm**

After a user adds a ticket:

1. Check if this event is already added in the current cart or not.
2. If not, add the selected event and ticket type to the cart.
3. If yes, check if this ticket type is already added to the cart before or not
   1. If not, add this property to the event item in the cart.
   2. If yes, find out the current quantity of that ticket type and manually accumulate the quantity.

</section>

<img src="/images/flash_ticketing-add_ticket.png" class="w-lg-50 mb-18">

<span class="text-primary">

[→ My source code of this algorithm](https://github.com/alysachan830/flash-ticketing/blob/main/pages/event/_eventId/tickets.vue)

</span>

</section>

</section>

<section>

## Challenge 2

**Calculate the total amount correctly**

<section class="mb-18">

The back-end calculates the total amount with the quantity property, not the value of a custom property.

In my case, I stored quantity of each ticket type with custom key and value, such as `{1625854073524,A區,正價票: 1}`. Because I did not store it with the given quantity property, the total amount was not calculated correctly. Worse still, if the user applied coupon, the discount value was calculated based on the total amount, which would be incorrect.

</section>

## Solution

**Manually calculate the quantity**

<section>

To have a correct total amount, I decided to manually calculate the quantity by adding up all the prices of the tickets in that event, and divide the total amount by the price of that event.

For example, if a user adds two ticket types of in an event, "夏日序曲 — 莫扎特的交響樂". Two custom properties will be added to the cart item:

- 1625891831522,A 區,正價票: 2
- 1625891831522,C 區,優惠票: 2

<section class="mb-18">
The data will be:

```json
"carts": [
    {
        "1625891831522,A區,正價票": 2,
        "1625891831522,C區,優惠票": 2,
        "final_total": 1152,
        "id": "-Mn-feaX5aMbyXZUrHrs",
        "product": {
            "category": "音樂",
            "dateTime": [
                {
                    "date": "2021-08-11",
                    "endTime": "13:30",
                    "startTime": "12:00",
                    "timestamp": 1625891831522
                },
                ...
            ],
            "discount": 80,
            "id": "-MeDhhevaeV5e8wUDUuS",
            "origin_price": 0,
            "price": 240,
            "ticketPrice": {
                "A": 240,
                "B": 360,
                "C": 420
            },
            "title": "夏日序曲 — 莫扎特的交響樂",
            ...
        },
        "product_id": "-MeDhhevaeV5e8wUDUuS",
        "qty": 4.8,
        "total": 1152
    }
]
```

</section>

After the user adds the ticket to the cart, I will calculate the quantity and send it back to server. In the example mentioned above, here is the calculation of the quantity:

    (240 * 2 + 420 * 2 * 0.8) / 240 = 4.8

Now I have the correct quantity. The back-end will help calculating the total amount:

    240 * 2 + 420 * 2 * 0.8 = 1152

<span class="text-primary">

[→ My source code of this algorithm](https://github.com/alysachan830/flash-ticketing/blob/main/pages/event/_eventId/tickets.vue)

</span>

In other words, the trick here is that the quantity is not the 'real' quantity. I only use it as a way to generate the correct total amount of all tickets in a single event in the cart.

</section>

</section>

<section>

## Summary

Although the workaround mentioned above may not be the best solution, thanks to the learning experience in the bootcamp, I start to realise:

1. In this project, I should have take the limitation and data structure of the APIs into consideration before I start deciding my data structure of each event and how to add different ticket types into the cart.

2. It is important to have suitable APIs for front-end development. Front-end developer is not only responsible for developing user interface and interaction, but also communicating with back-end developers for helping to design the most suitable APIs.

</section>

</section>
