---
layout: posts
title:  "ORM: joins vs includes"
---

### joins
{% highlight ruby %}
Trip.joins(:schedules)
# Trip Load (1.6ms)
# SELECT "trips".* FROM "trips" INNER JOIN "schedules" ON "schedules"."trip_id" = "trips"."id" 
# /* loading for inspect */ LIMIT $
{% endhighlight %}

### includes
{% highlight ruby %}
Trip.includes(:schedules)
# Trip Load (0.5ms)  
# SELECT "trips".* FROM "trips" 
# /* loading for inspect */ LIMIT $1  [["LIMIT", 11]]

# Schedule Load (0.3ms)  
# SELECT "schedules".* FROM "schedules" WHERE "schedules"."trip_id" IN ($1, $2, $3, $4, $5, $6, $7, $8, $9, $10, $11)
{% endhighlight %}