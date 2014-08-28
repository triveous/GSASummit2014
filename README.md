GSASummit2014
=============

###Features
- DealsAPI - A Java endpoint implementation for AppEngine
- app - An android client that consumes the above API

###DealsAPI
- This is a simple endpoint that in turn consumes a 3rd party custom deals API from Kiminolabs and gosf.coupondunia.in
- Then it creates a simple string based list which in turn becomes the content for this endpoint, this will be consumed by the android app

Kimonolabs deals URL: https://www.kimonolabs.com/api/3hp54bog?apikey=ZdSnJCoFzxb1gjUS3m9wSx97NrSPDbdQ

###Sample response:

```json
{
  "name": "gosf",
  "count": 30,
  "frequency": "Monthly",
  "version": 2,
  "newdata": false,
  "lastrunstatus": "success",
  "thisversionrun": "Thu Aug 28 2014 11:23:47 GMT+0000 (UTC)",
  "lastsuccess": "Thu Aug 28 2014 11:23:47 GMT+0000 (UTC)",
  "nextrun": "Mon Sep 01 2014 00:00:00 GMT+0000 (UTC)",
  "results": {
    "collection1": [
      {
        "title": "Jabong Flat 40% Coupon on minimum purchase of Rs. 2499",
        "category": {
          "text": "Fashion",
          "href": "http://gosf.coupondunia.in/category/fashion"
        },
        "code": "GOSF40"
      },
      {
        "title": "Myntra Flat 35% Off Coupon With No Minimum Purchase",
        "category": {
          "text": "Fashion",
          "href": "http://gosf.coupondunia.in/category/fashion"
        },
        "code": "GOSF35"
      },
      {
        "title": "Minimum Rs. 500 and upto 40% off on mobile phones",
        "category": {
          "text": "Mobiles & Tablets",
          "href": "http://gosf.coupondunia.in/category/mobiles-and-tablets"
        },
        "code": ""
      },
      {
        "title": "Flat 35% Off On Domestic & International Hotels Bookings (max discount of Rs 4000/-)",
        "category": {
          "text": "Travel",
          "href": "http://gosf.coupondunia.in/category/travel"
        },
        "code": "GOSFGO"
      }
    ]
  }
}
```

is simplified to 

```json
{
 "data": [
  "Jabong Flat 40% Coupon on minimum purchase of Rs. 2499",
  "Myntra Flat 35% Off Coupon With No Minimum Purchase",
  "Minimum Rs. 500 and upto 40% off on mobile phones",
  "Flat 35% Off On Domestic & International Hotels Bookings (max discount of Rs 4000/-)",
 ]
}
```

###App
- Simple android app with a ListActivity
- Consumes the above endpoint using Cloud Endpoints
- Shows the result in the ListActivity

###App output
![alt text](http://s29.postimg.org/a14hje13b/device_2014_08_28_225710.png "The ListActivity with the deals")
