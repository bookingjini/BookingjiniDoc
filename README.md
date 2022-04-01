<!-- Bookingjini Docs -->

### Bookingjini Docs

- Complete Business Solutions For Hotel Booking System.
- Bringing the best Booking Software for you, the expanded range of innovative products & make the best decision for your hotels.

## What is Booking [17 Jan 2022]

A booking is the arrangement that you make when you book something such as a hotel room, a table at a restaurant, a theatre seat, or a place on public transport.

In hopitality & travel domain Bookingjini works only on the Stay domain for the time being concern. 

#### Booking Consist Of Two Parts

|      Header     |        Body         |
| --------------- | ------------------- |
| Booking ID      | Room Type           |
| Booking Date    | Booker Information  |
| Booking Time    |                     |
| Booking Amount  |                     |
| Paid Amount     |                     |
| Check In        |                     |
| Check Out       |                     |

## Key Points

- Early Check-In can be availed by the guest by paying an extra amount to the hotel.
- Late Check-Out can be avail by the guest by paying an extra amount to the hotelier.
- Booking.com is the only OTA that provides pay at hotel option.
- No show can be only done in walk-in and this is applied when the guest does not come to the hotel at the check-in time.
- Check-out date can never be before Check-in date
- The cancellation policy will only be defined by the hotelier.

**MICE - Meetings, Incentives, Conferences and Events/Exhibitions**

**PAX - Per Person**

## Check-In & Check-Out [18 Jan 2022]

- Nights = CheckOut - CheckIn (This calculated with the system timestamp)
- In same day CheckOut the CheckIn and CheckOut dates are same.
- If CheckIn and CheckOut dates are same we consider the number of nights as 1 not 0.
- One day back CheckIn is only allowed in Walk-in.
- Hourly booking can only be availed in same day CheckOut.

#### LOS (Length of Stay)

- The maximum number of nights a guest can stay. (Max LOS)
- The minimum number of nights a guest can stay. (Min LOS)

#### Minimum Advanced Booking Date

- The minimum number of days before the guest can book.

#### Maximum Advanced Booking Date

- The maximum number of days before the guest can book.

## Room Types [19 Jan 2022]

- Amenities can be of two types
  - Based on Hotel
  - Based on Room Type

- Room Nights = Number of Rooms x Number of Nights

  `Example: 6 Rooms x 2 Nights = 12 Room Nights`

- **ARI - Availability of Rate and Inventory**
- Rate is always excluding of GST and it is only for per room and per night.

#### GST Slab

|      Amount     |        Percentage   |
| --------------- | ------------------- |
| 0 - 1000        |        0%           |
| 1001 - 7500     |        12%          |
| > 7500          |        18%          |


`Example: CheckIn[2 Aug 22] - CheckOut[4 Aug 22]`

|  Rooms  |  Room Type          |  Rate   |  Discount   |  Discount Amount   |  Selling Price   |  Nights  |  Room Nights  |  Room Price  |  GST  | GST Amount | Room Price  |
| ------- | ------------------- | ------- | ----------- | ------------------ | ---------------- | -------- | ------------- | ------------ | ----- | ---------- | ----------- |
|    2    |  Deluxe Room        |  3000   |     5%      |        150         |        2850      |     2    |       4       |    11400     |  12%  |    1368    |    12768    | 
|    3    |  Premium Room       |  5000   |     2%      |        100         |        4900      |     2    |       6       |    29400     |  12%  |    3528    |    32928    |
|    1    |  Presidential Room  |  15000  |     50%     |        7500        |        7500      |     2    |       2       |    15000     |  12%  |    1800    |    16800    |

- GST Slab will be decided by the selling price and then it gets applied to the total room price.
- The rate can be different on different dates.
- After GST amount discount does not apply.
- The selling price is also known as after discount amount.
- Room Rate can vary on 4 different factors
  - Date 
  - Room Type
  - Meal Plan
  - Occupancy

## Inventory [20 Jan 2022]

- Inventory = Number of Room Nights

  `Example - Blue Moon Resort has 75 Room out of which Deluxe Rooms are 35 and Premium Suite Room are 40`
  - For every new booking inventory gets minus.
  - For cancellation booking inventory gets added.
  
  Say for example on 2 and 3 of august there comes a new booking for 2 room nights. So on 2 and 3 the inventory for a deluxe room and the premium room gets subtracted. That is the new booking will minus the inventory.
  
   |   Room Type   |   1   |         2         |         3       |   4   |   5   |   6   |       |  1 Mon  |  2 Tue  |  3 Wed  |  4 Thu  |  5 Fri  |  6 Sat  |
   | ------------- | ----- | ----------------- | --------------- | ----- | ----- | ----- | ----- | ------- | ------- | ------- | ------- | ------- | ------- |
   | Deluxe Room   |   35  |   <s>35</s> 33    |   <s>35</s> 33  |   35  |   35  |   35  | ----- |   3000  |   3000  |   4000  |   3500  |   3000  |  3000   |
   | Premium Room  |   40  |   <s>40</s> 37    |   <s>40</s> 37  |   40  |   40  |   40  | ----- |   5000  |   5000  |   8000  |   7000  |   5000  |  5000   |
   
- Every booking can have three status
  - New reservation or booking (For new booking inventory gets minus)
  - Cancellation of booking (For cancellation, inventory gets added)
  - Modification of booking

  ```
  Example -
     Current Booking - 2 August to 4 August (2 Room Nights)
     New Booking - 3 August to 5 August (2 Room Nights)
  ```
  
  |      Day     |       Day     |
  | ------------ | ------------- |
  |     + 2      |   <s>3</s> +  |
  |  - <s>3</s>  |       4 -     |
  
  - Booking Voucher consists of the following details
   - Each Room Types
   - Each Room Nights
   - Each Room
 
## Meal Plan [21 Jan 2022]

- A meal plan is a plan that is added to a room rate for providing a room and meals to guests at a hotel.

|    Meal Plan                    |    Description                      |
| ------------------------------- | ----------------------------------- |
| EP (European Plan)              | Room Only                           |
| CP (Continental Plan)           | Room + Breakfast                    |
| AP (American Plan)              | Room + Breakfast + Lunch + Dinner   |
| MAP (Modified American Plan)    | Room + Breakfast + Lunch Or Dinner  |


`Example - Rate Plan`

|  Room Type    |  Meal Plan  |   Day  |   Day  |   Day  |   Day  |   Day  |   Day  |
| ------------- | ----------- | ------ | ------ | ------ | ------ | ------ | ------ |
| Deluxe Room   | EP          |  3000  |  3000  |  3000  |  3000  |  3000  |  3000  |
| Deluxe Room   | CP          |  3500  |  3500  |  3500  |  3500  |  3500  |  3500  |
| Premium Room  | EP          |  4000  |  4000  |  4000  |  4000  |  4000  |  4000  |
| Premium Room  | CP          |  5600  |  5600  |  5600  |  5600  |  5600  |  5600  |
  
## Occupancy [24 Jan 2022]

- Occupancy is the number of guests staying in a room, sometimes directly referred to as "occupants".
- Maximum Occupancy is the maximum amount of guests that can stay in a room.
- Room size defines the occupancy of a room.
  
  `Example - Single Occupancy, Double Occupancy, etc.`

**BAR - Best Available Rates**

## Booking [1 Mar 2022]

- Booking Status
  - Reservation of booking
  - Cancellation of booking
  - Modification of booking

`Example: Guest - Reservation (Confirrmed)
                - Cancellation (Cancelled)
                - Modification (Modified)`

Inventory status on booking
  - Confirmed ( - )
  - Cancelled ( + )
  - Modified ( +/- )

- Booking id will be same for all the above stages of bookings.
- Modification can also be treated as cancellation or reservation.

|   Check In    |   Check Out  |       Stay     |
| ------------- | ------------ | -------------- |
| 3             | 5            | 3 [+], 4 [+/-] |
| 7             | 9            | 7 [-], 8 [-]   |
| 4             | 6            | 4 [-], 5 [-]   |

- Guest can book a room night by doing a prepaid booking
- Or guest can book a room night by paying at the hotel

## Software Requirement of a Hotel [3 Mar 2022]

- A hotel sells a room nights.

- Softwares
  - Website (for online presence)
  - Online Channels
    - Booking Engine
    - Booking.com
    - Goibibo
    - Expedia
    - Agoda
    - AirBnb
  - Channel Manager (Manages Channels)
  - PMS (Property Management System)
    - Front Office
    - F & B
    - Housekeeping
    - Maintenance
    - Finance (Sale)
    - Expense (Purchase)
  - CRS (Central Reservation System)
  - HRMS (Human Resources Management System)
  - CRM (Customer relationship management)
  - ChatBot
  - Rate Shopper
  - Digital Marketing Automation

`As of now Booking Engine and Channel Manager are core product of BookingJini [23-3-2022]`

## Channel Manager [1 Apr 2022]

A hotel channel manager is a tool designed to help hotel owners effectively manage customer data, online inventory and price rates.

Channel managers develop, service, and grow relationships with channel partners. The role includes duties such as developing sales strategies, negotiating with partners, and training and developing their sales teams. Channel partners are often middle-management.

The PMS and channel manager integration is quite crucial to ensure the success of your online distribution effort. When there is a seamless and two-way integration a Hotel PMS and a channel manager, rates and availability from the Hotel PMS will automatically be pushed to the channel management platform for distribution across all the connected OTAs. Similarly, bookings on OTAs would also get instantaneously updated on the Hotel PMS delivered through the channel manager. This ensures that there is no discrepancy in the availability of rooms on various channels. Similarly, this integration updates reservation cancellations and modifications on all the sales channels. This helps you know in real-time how many rooms you have to sell. Considering this, you can either have a plan to overbook your property with caution or you can completely avoid overbookings.

Similarly, the integration between your PMS and a booking engine can help you a lot when you plan to grow your direct bookings. As soon as you receive a booking through your website, the Hotel PMS gets updated instantly. In case of booking modification, room upgrade or cancellation (only bookings coming via the booking engine), this integration updates the PMS. This enables your reservation staff/front desk staff to know your hotel’s availability and room status in real-time. This too, helps you avoid overbooking and double booking.

## How Channel manager Works

- Use a channel manager to save time and increase exposure.
	A channel manager is a key tool for keeping distribution simple. With a channel manager you can manage your distribution channels in one place and easily stay on top of bookings. Simply look at your channel manager and you will see your bookings from channels including OTAs, point of sale, partners and agents, and your own online booking system. You can also use the Bookingjini Channel Manager to quickly adjust your capacity across all channels if your availability suddenly changes.

- One of the main advantages of using a channel manager is live inventory. This allows you to distribute only your available tours and activities and keep your availability up-to-date on all channels. This allows you to maximize revenue and prevent embarrassing overbooking incidents: the last thing you want when you're increasing your distribution efforts.

- Minimize admin with real-time pricing Choose a channel manager with real-time pricing and you'll avoid the hassle of having to make alterations on individual OTAs. Not only is double data entry boring and time-consuming, but it also doubles your team's risk of manual error. Your channel manager should also permit you to launch a last-minute sale on an OTA: a smart strategy if you want to sell more quickly than you could on your own website.
  

- **OTAs**

   OTAs are third-party agencies who sell hotel rooms on their websites to guests. A guest logs in to an OTA, selects a hotel, checks out rates and availability before    making the final reservation. OTAs help you sell more rooms via their websites – called indirect booking. For each booking you receive from an OTA, you need to pay    a booking commission based on the agreement. You can choose to work with leading OTAs to drive more indirect bookings and you can even select popular OTAs in a        specific region as part of your online distribution effort.

#### Manage OTA in Channel Manager

- Updates tour information price and availibility.
- Long cut off time needed to process booking in the backend.
- Copy booking each ota to our system.
- Add each booking to our reporting system for generateing report monthly.
- inventory is always updated in real time to all ota.









