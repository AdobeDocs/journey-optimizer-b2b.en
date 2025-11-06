---
title: Helper functions
description: Helper functions list
---
# Helper functions

Use the Helper functions within the personalization editor to define personalized content experiences with precision and efficiency by manipulating data, performing calculations, and formatting content. Explore and experiment with these functions, operators, and helpers to discover how they work together to help you craft tailored, data-driven journeys.

## Aggregation functions

Use aggregation functions to group multiple values to form a single summary value. You can also use array and list functions to define interactions with arrays, lists, and strings easier.

### average {#average}

Use the `average` function to return the arithmetic mean of all the selected values within the array.

+++Syntax

```sql
{%= average(array) %}
```

**Example**

The following operation returns the average price of all the orders.

```sql
{%=average(orders.order.price)%}
```

+++

### count {#count}

Use the `count` function to return the number of elements within the given array.

+++Syntax

```sql
{%= count(array) %}
```

**Example**

The following operation returns the number of orders in the array.

```sql
{%= count(orders) %}
```

+++

### max {#max}

Use the `max` function to return the largest of all the selected values within the array.

+++Syntax

```sql
{%= max(array) %}
```

**Example**

The following operation returns the highest price of all the orders.

```sql
{%=max(orders.order.price)%}
```

+++

### min {#min}

Use the `min` function to return the smallest of all the selected values within the array.

+++Syntax

```sql
{%= min(array) %}
```

**Example**

The following operation returns the lowest price of all the orders.

```sql
{%=min(orders.order.price) %}
```

+++

### sum {#sum}

Use the `sum` function to return the sum of all the selected values within the array.

+++Syntax

```sql
{%= sum(array) %}
```

**Example**

The following operation returns the sum of all the orders' prices.

```sql
 {%=sum(orders.order.price)%}
```

+++

## Arithmetic functions {#maths}

Use arithmetic functions to perform basic calculations on values.

### add {#add}

Use the `+` (addition) function to find the sum of two argument expressions.

+++Syntax

```sql
{%= double + double %}
```

**Example**

The following operation sums the price of two different products.

```sql
{%= product1.price + product2.price %}
```

+++

### multiply {#multiply}

Use the `*` (multiplication) function to find the product of two argument expressions.

+++Syntax

```sql
{%= double * double %}
```

**Example**

The following operation finds the product of the inventory and the price of a product to find the gross value of the product.

```sql
{%= product.inventory * product.price %}
```

+++

### subtract {#substract}

Use the `-` (subtraction) function to find the difference of two argument expressions.

+++Syntax

```sql
{%= double - double %}
```

**Example**

The following operation finds the difference in price between two different products.

```sql
{%= product1.price - product2.price %}
```

+++

### divide {#divide}

Use the `/` (division) function to find the quotient of two argument expressions.

+++Syntax

```sql
{%= double / double %}
```

**Example**

The following operation finds the quotient between the total products sold and total money earned to see the average cost per item.

```sql
{%= totalProduct.price / totalProduct.sold %}
```

+++

### remainder {#remainder}

Use the `%` (remainder) function to find the remainder after dividing the two argument expressions. 

+++Syntax

```sql
{%= double % double %}
```

**Example**

The following operation checks if the person's age is divisible by five.

```sql
{%= person.age % 5 = 0 %}
```

+++

## Arrays and list functions {#arrays}

Use these functions to make interaction with arrays, lists, and strings easier.

### countOnlyNull {#count-only-null}

Use the `countOnlyNull` function to count the number of null values in a list.

+++Syntax

```sql
{%= countOnlyNull(array) %}
```

**Example**

```sql
{%= countOnlyNull([4,0,1,6,0,0]) %}
```

Returns 3.

+++

### countWithNull {#count-with-null}

Use the `countWithNull` function to count all the elements of a list including null values.

+++Syntax

```sql
{%= countWithNull(array) %}
```

**Example**

```sql
{%= countOnlyNull([4,0,1,6,0,0]) %}
```

Returns 6.

+++

### distinct {#distinct}

Use the `distinct` function to get values from an array or list with duplicate values removed.

+++Syntax

```sql
{%= distinct(array) %}
```

**Example**

The following operation specifies people who have placed orders in more than one store.

```sql
{%= distinct(person.orders.storeId).count() > 1 %}
```

+++

### distinctCountWithNull {#distinct-count-with-null}

Use the `distinctCountWithNull` function to count the number of different values in a list including the null values.

+++Syntax

```sql
{%= distinctCountWithNull(array) %}
```

**Example**

```sql
{%= distinctCountWithNull([10,2,10,null]) %}
```

Returns 3.

+++

### head {#head}

Use the `head` function to return the first item in an array or list.

+++Syntax

```sql
{%= head(array) %}
```

**Example**

The following operation returns the first of the top five orders with the highest price. More information about the `topN` function can be found in the [first `n` in array](#first-n) section.

```sql
{%= head(topN(orders,price, 5)) %}
```

+++

### topN {#first-n}

The `topN` function sorts an array in descending order based on the given numerical expression and returns the first `N` items. If the array size is less than `N`, it returns the entire sorted array.

+++Syntax

```sql
{%= topN(array, value, amount) %}
```

| Argument | Description |
| --------- | ----------- |
| `{ARRAY}` | The array or list to sort. |
| `{VALUE}` | The property used to sort the array or list. |
| `{AMOUNT}` | The number of items to return. |

**Example**

The following operation returns the first five orders with the lowest price.

```sql
{%= topN(orders,price, 5) %}
```

+++

### in {#in}

Use the `in` function to determine if an item is a member of an array or list.

+++Syntax

```sql
{%= in(value, array) %}
```

**Example**

The following operation defines people with birthdays in March, June, or September.

```sql
{%= in (person.birthMonth, [3, 6, 9]) %}
```

+++

### includes {#includes}

Use the `includes` function to determine if an array or list contains a given item.

+++Syntax

```sql
{%= includes(array,item) %}
```

**Example**

The following operation defines people whose favorite color includes red.

```sql
{%= includes(person.favoriteColors,"red") %}
```

+++

## intersects {#intersects}

The `intersects` function is used to determine if two arrays or lists have at least one common member.

+++Syntax

```sql
{%= intersects(array1, array2) %}
```

**Example**

The following operation defines people whose favorite colors include at least one of red, blue, or green.

```sql
{%= intersects(person.favoriteColors,["red", "blue", "green"]) %}
```

+++

<!-- ## Intersection{#intersection}

The `intersection` function is used to determine the common members of two arrays or lists.

**Syntax**

```sql
intersection({ARRAY},{ARRAY})
```

**Example**

The following operation defines if person 1 and person 2 both have favorite colors of red, blue, and green.

```sql
intersection(person1.favoriteColors,person2.favoriteColors) = ["red", "blue", "green"]
```
--> 

### bottomN {#last-n}

The `bottomN` function sorts an array in ascending order based on the given numerical expression and returns the first `N` items. If the array size is less than `N`, it returns the entire sorted array.

+++Syntax

```sql
{%= bottomN(array, value, amount) %}
```

| Argument | Description |
| --------- | ----------- | 
| `{ARRAY}` | The array or list to sort. |
| `{VALUE}` | The property used to sort the array or list. |
| `{AMOUNT}` | The number of items to return. |

**Example**

The following operation returns the last five orders with the highest price.

```sql
{%= bottomN(orders,price, 5) %}
```

+++

### notIn {#notin}

Use the `notIn` function to determine if an item is not a member of an array or list.

>[!NOTE]
>
>The `notIn` function *also* ensures that neither value is equal to null. Therefore, the results are not an exact negation of the `in` function.

+++Syntax

```sql
{%= notIn(value, array) %}
```

**Example**

The following operation defines people with birthdays that are not in March, June, or September.

```sql
{%= notIn(person.birthMonth ,[3, 6, 9]) %}
```

+++

### subsetOf {#subset}

Use the `subsetOf` function to determine if a specific array (array A) is a subset of another array (array B). In other words, that all elements in array A are elements of array B.

+++Syntax

```sql
{%= subsetOf(array1, array2) %}
```

**Example**

The following operation defines people who have visited all of their favorite cities.

```sql
{%= subsetOf(person.favoriteCities,person.visitedCities) %}
```

+++

### supersetOf {#superset}

Use the `supersetOf` function to determine if a specific array (array A) is a superset of another array (array B). In other words, that array A contains all elements in array B.

+++Syntax

```sql
{%= supersetOf(array1, array2) %}
```

**Example**

The following operation defines people who have eaten sushi and pizza at least once.

```sql
{%= supersetOf(person.eatenFoods,["sushi", "pizza"]) %}
```

+++

## Date and time functions {#date-time}

Use the date and time functions to perform date and time operations on values.

### addDays {#add-days}

The `addDays` function adjusts a given date by a specified number of days, using positive values to increment and negative values to decrement.

+++Syntax

```sql
{%= addDays(date, number) %}
```

**Example**

* Input: `{%= addDays(stringToDate("2024-11-01T17:19:51Z"),10) %}`
* Output: `2024-11-11T17:19:51Z`

+++

### addHours {#add-hours}

The `addHours` function adjusts a given date by a specified number of hours, using positive values to increment and negative values to decrement.

+++Syntax

```sql
{%= addHours(date, number) %}
```

**Example**

* Input: `{%= addHours(stringToDate("2024-11-01T17:19:51Z"),1) %}`
* Output: `2024-11-01T18:19:51Z`

+++

### addMinutes {#add-minutes}

The `addMinutes` function adjusts a given date by a specified number of minutes, using positive values to increment and negative values to decrement.

+++Syntax

```sql
{%= addMinutes(date, number) %}
```

**Example**

* Input: `{%= addMinutes(stringToDate("2024-11-01T17:59:51Z"),10) %}`
* Output: `2024-11-01T18:09:51Z`

+++

### addMonths {#add-months}

The `addMonths` function adjusts a given date by a specified number of months, using positive values to increment and negative values to decrement.

+++Syntax

```sql
{%= addMonths(date, number) %}
```

**Example**

* Input: `{%= addMonths(stringToDate("2024-11-01T17:19:51Z"),2) %}`
* Output: `2025-01-01T17:19:51Z`

+++

### addSeconds {#add-seconds}

The `addSeconds` function adjusts a given date by a specified number of seconds, using positive values to increment and negative values to decrement.

+++Syntax

```sql
{%= addSeconds(date, number) %}
```

**Example**

* Input: `{%= addSeconds(stringToDate("2024-11-01T17:19:51Z"),10) %}`
* Output: `2024-11-01T17:20:01Z`

+++

### addYears {#add-years}

The `addYears` function adjusts a given date by a specified number of years, using positive values to increment and negative values to decrement.

+++Syntax

```sql
{%= addYears(date, number) %}
```

**Example**

* Input: `{%= addYears(stringToDate("2024-11-01T17:19:51Z"),2) %}`
* Output: `2026-11-01T17:19:51Z`

+++

### age {#age}

Use the `age` function to retrieve the age from a given date.

+++Syntax

```sql
 {%= age(datetime) %}
```

<!--
**Example**

The following operation gets the value of the identity map for the key `example@example.com`.

```sql
 {%= age(datetime) %}
```
-->

+++

### ageInDays {#age-days}

The `ageInDays` function calculates the number of days elapsed between the given date and the current date. It uses negative for future dates and positive for past dates.

+++Syntax

```sql
{%= ageInDays(date) %}
```

**Example**

currentDate = 2025-01-07T12:17:10.720122+05:30 (Asia/Kolkata)

* Input: `{%= ageInDays(stringToDate("2025-01-01T17:19:51Z"))%}`
* Output: `5`

+++

### ageInMonths {#age-months}

The `ageInMonths` function calculates the number of months elapsed between the given date and the current date. It uses negative for future dates and positive for past dates.

+++Syntax

```sql
{%= ageInMonths(date) %}
```

**Example**

currentDate = 2025-01-07T12:22:46.993748+05:30(Asia/Kolkata)

* Input: `{%=ageInMonths(stringToDate("2024-01-01T00:00:00Z"))%}`
* Output: `12`

+++

### compareDates {#compare-dates}

The `compareDates` function compares the first input date with the other. It returns 0 if date1 is equal to date2, -1 if date1 comes before date2, and 1 if date1 comes after date2.

+++Syntax

```sql
{%= compareDates(date1, date2) %}
```

**Example**

* Input: `{%=compareDates(stringToDate("2024-12-02T00:00:00Z"), stringToDate("2024-12-03T00:00:00Z"))%}`
* Output: `-1`

+++

### convertZonedDateTime {#convert-zoned-date-time}

The `convertZonedDateTime` function converts a date-time to a given timezone.

+++Syntax

```sql
{%= convertZonedDateTime(dateTime, timezone) %}
```

**Example**

* Input: `{%=convertZonedDateTime(stringToDate("2019-02-19T08:09:00Z"), "Asia/Tehran")%}`
* Output: `2019-02-19T11:39+03:30[Asia/Tehran]`

+++

### currentTimeInMillis {#current-time}

Use the `currentTimeInMillis` function to retrieve current time in epoch milliseconds.

+++Syntax

```sql
{%= currentTimeInMillis() %}
```

<!--
**Example**

The following operation gets all the keys for the map `identityMap`.

```sql
{%= keys(identityMap) %}
```
-->

+++

### dateDiff {#date-diff}

Use the `dateDiff` function to retrieve the difference between two dates in number of days.

+++Syntax

```sql
{%= dateDiff(datetime,datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

+++

### dayOfMonth {#day-month}

The `dayOfMonth` returns the number representing the day of the month.

+++Syntax

```sql
{%= dayOfMonth(datetime) %}
```

**Example**

* Input: `{%= dayOfMonth(stringToDate("2024-11-05T17:19:51Z")) %}`
* Output: `5`

+++

### DayOfWeek {#day-week}

Use the `dayOfWeek` function to retrieve the day of week.

+++Syntax

```sql
{%= dayOfWeek(datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

+++

### dayOfYear {#day-year}

Use the `dayOfYear` function to retrieve the day of year.

+++Syntax

```sql
{%= dayOfYear(datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

+++

### diffInSeconds {#diff-seconds}

The `diffInSeconds` function returns the difference between two dates in terms of seconds.

+++Syntax

```sql
{%= diffInSeconds(endDate, startDate) %}
```

**Example**

* Input: `{%=diffInSeconds(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2024-11-01T17:19:01Z"))%}`
* Output: `50`

+++

### extractHours {#extract-hours}

The `extractHours` function extracts the hour component from a given timestamp.

+++Syntax

```sql
{%= extractHours(date) %}
```

**Example**

* Input: `{%= extractHours(stringToDate("2024-11-01T17:19:51Z"))%}`
* Output: `17`

+++

### extractMinutes {#extract-minutes}

The `extractMinutes` function extracts the minute component from a given timestamp.

+++Syntax

```sql
{%= extractMinutes(date) %}
```

**Example**

* Input: `{%= extractMinutes(stringToDate("2024-11-01T17:19:51Z"))%}`
* Output: `19`

+++

### extractMonths {#extract-months}

The `extractMonth` function extracts the month component from a given timestamp.

+++Syntax

```sql
{%= extractMonths(date) %}
```

**Example**

* Input: `{%=extractMonth(stringToDate("2024-11-01T17:19:51Z"))%}`
* Output: `11`

+++

### extractSeconds {#extract-seconds}

The `extractSeconds` function extracts the second component from a given timestamp.

+++Syntax

```sql
{%= extractSeconds(date) %}
```

**Example**

* Input: `{%=extractSeconds(stringToDate("2024-11-01T17:19:51Z"))%}`
* Output: `51`

+++

### formatDate {#format-date}

Use the `formatDate` function to format a date time value. The format should be a valid Java `DateTimeFormat` pattern.

+++Syntax

```sql
{%= formatDate(datetime, format) %}
```

Where the first string is the date attribute and the second value is how you want the date to be converted and displayed.

>[!NOTE]
>
> If a date pattern is invalid, the date falls back to ISO standard format.
>
> You can use Java date formatting functions as summarized in [Oracle documentation](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html){_blank}

**Example**

The following operation returns the date in the following format: MM/DD/YY.

```sql
{%= formatDate(profile.timeSeriesEvents._mobile.hotelBookingDetails.bookingDate, "MM/dd/YY") %}
```

+++

#### Pattern characters {#pattern-characters}

Some pattern letters may look similar, but represent different concepts.

| Pattern | Meaning | Example (for `2023-12-31T10:15:30Z`) |
|---------|---------|--------------------------------------|
| `y`     | Calendar year (standard year) | `2023` |
| `Y`     | Week-based year (ISO 8601). It may differ at year boundaries. | `2024` (December 31, 2023 falls in the first week of 2024) |
| `M`     | Month-of-year (1–12 or text like `Jan`, `January`) | `12` or `Dec` |
| `m`     | Minute-of-hour (0–59) | `15` |
| `d`     | Day-of-month (1–31) | `31` |
| `D`     | Day-of-year (1–366) | `365` |

### Format date with locale support {#format-date-locale}

You can use the `formatDate` function to format a date time value into its corresponding language sensitive representation, such as for a desired locale. The format should be a valid Java `DateTimeFormat` pattern.

+++Syntax

```sql
{%= formatDate(datetime, format, locale) %}
```

Where the first string is the date attribute, the second value is how you want the date to be converted and displayed, and the third value represents the locale in string format.

>[!NOTE]
>
> If a date pattern is invalid, the date falls back to ISO standard format.
>
> You can use Java date formatting functions as summarized in the [Oracle documentation](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html).
>
> You can use formatting and valid locales as summarized in the [Oracle documentation](https://docs.oracle.com/javase/8/docs/api/java/util/Locale.html) and [Supported locales](https://www.oracle.com/java/technologies/javase/jdk11-suported-locales.html).

**Example**

The following operation returns the date in the following format: MM/dd/YY and locale FRANCE.

```sql
{%= formatDate(profile.timeSeriesEvents._mobile.hotelBookingDetails.bookingDate, "MM/dd/YY", "fr_FR") %}
```

+++

### getCurrentZonedDateTime {#get-current-zoned-date-time}

The `getCurrentZonedDateTime` function returns the current date and time with time zone information.

+++Syntax

```sql
{%= getCurrentZonedDateTime() %}
```

**Example**

* Input: `{%= getCurrentZonedDateTime() %}`
* Output: `2024-12-06T17:22:02.281067+05:30[Asia/Kolkata]`

+++

### diffInHours {#hours-difference}

The `diffInHours` function returns the difference between two dates in terms of hours.

+++Syntax

```sql
{%= diffInHours(endDate, startDate) %}
```

**Example**

* Input: `{%= diffInHours(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2024-11-01T07:19:51Z"))%}`
* Output: `10`

+++

### diffInMinutes {#diff-minutes}

The `diffInMinutes` function returns the difference between two dates in terms of minutes.

+++Syntax

```sql
{%= diffInMinutes(endDate, startDate) %}
```

**Example**

* Input: `{%= diffInMinutes(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2024-11-01T16:19:51Z"))%}`
* Output: `60`

+++

### diffInMonths {#months-difference}

The `diffInMonths` function returns the difference between two dates in terms of months.

+++Syntax

```sql
{%= diffInMonths(endDate, startDate) %}
```

**Example**

* Input: `{%=diffInMonths(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2024-08-01T17:19:51Z"))%}`
* Output: `3`

+++

### setDays {#set-days}

Use the `setDays` function to set the day of the month for the given date-time.

+++Syntax

```sql
{%= setDays(datetime, day) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

+++

### SetHours {#set-hours}

Use the `setHours` function to set the hour of the date-time.

+++Syntax

```sql
{%= setHours(datetime, hour) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

+++

### toDateTime {#string-to-date-time}

The `toDateTime` function converts string to date. It returns the epoch date as output for invalid input.

+++Syntax

```sql
{%= toDateTime(string, string) %}
```

**Example**

* Input: `{%=toDateTime("2024-11-01T17:19:51Z")%}`
* Output: `2024-11-01T17:19:51Z`

+++

### toUTC {#to-utc}

Use the `toUTC` function to convert a datetime to UTC.

+++Syntax

```sql
{%= toUTC(datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

+++

### truncateToStartOfDay {#truncate-day}

Use the `truncateToStartOfDay` function to modify a given date-time by setting it to the start of the day with time at 00:00.

+++Syntax

```sql
{%= truncateToStartOfDay(date) %}
```

**Example**

* Input: `{%= truncateToStartOfDay(stringToDate("2024-11-01T17:19:51Z")) %}`
* Output: `2024-11-01T00:00Z`

+++

### truncateToStartOfQuarter {#truncate-quarter}

Use the `truncateToStartOfQuarter` function is used to truncate a date-time to the first day of its quarter (such as January 1, April 1, July 1, October 1) at 00:00.

+++Syntax

```sql
{%= truncateToStartOfQuarter(dateTime) %}
```

**Example**

* Input: `{%=truncateToStartOfQuarter(stringToDate("2024-11-01T17:19:51Z"))%}`
* Output: `2024-10-01T00:00Z`

+++

### truncateToStartOfWeek {#truncate-week}

The `truncateToStartOfWeek` function modifies a given date-time by setting it to the start of the week (Monday at 00:00).

+++Syntax

```sql
{%= truncateToStartOfWeek(dateTime) %}
```

**Example**

* Input: `{%= truncateToStartOfWeek(stringToDate("2024-11-19T17:19:51Z"))%} // tuesday`
* Output: `2024-11-18T00:00Z // monday`

+++

### truncateToStartOfYear {#truncate-year}

Use the `truncateToStartOfYear` function to modify a given date-time by truncating it to the first day of the year (January 1) at 00:00.

+++Syntax

```sql
{%= truncateToStartOfYear(dateTime) %}
```

**Example**

* Input: `{%=truncateToStartOfYear(stringToDate("2024-11-01T17:19:51Z"))%}`
* Output: `2024-01-01T00:00Z`

+++

### weekOfYear {#week-of-year}

Use the `weekOfYear` function to retrieve the week of the year.

+++Syntax

```sql
{%= weekOfYear(datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

+++

### diffInYears {#diff-years}

Use the `diffInYears` function to return the difference between two dates in terms of years.

+++Syntax

```sql
{%= diffInYears(endDate, startDate) %}: int
```

**Example**

* Input: `{%=diffInYears(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2019-10-01T17:19:51Z"))%}`
* Output: `5`

+++

## Operator functions {#operators}

Use the Boolean and comparison functions to perform logical evaluations.

### and {#and}

The `and` function is used to create a logical conjunction.

+++Syntax

```sql
{%= query1 and query2 %}
```

**Example**

The following operation returns all people with home country (France) and birth year (1985).

```sql
{%= profile.homeAddress.country = "France" and profile.person.birthYear = 1985 %}
```

+++

### or {#or}

The `or` function is used to create a logical disjunction.

+++Syntax

```sql
{%= query1 or query2 %}
```

**Example**

The following operation returns all people with home country (France) or birth year (1985).

```sql
{%= profile.homeAddress.country = "France" or profile.person.birthYear = 1985 %}
```

+++

<!--
## Not{#not}

The `not` (or `!`) function is used to create a logical negation.

**Syntax**

```sql
not ({QUERY})
!({QUERY})
```

**Example**

The following operation will return all people who do not have their home country as Canada.

```sql
not (homeAddress.countryISO = "CA")
```
-->

### equals {#operator-equals}

The `=` (equals) function checks whether one value or expression is equal to another value or expression.

+++Syntax

```sql
{%= expression = value %}
```

**Example**

The following operation checks if the home address country is France.

```sql
{%= profile.homeAddress.country = "France" %}
```

+++

### not equal {#notequal}

The `!=` (not equal) function checks whether one value or expression is **not** equal to another value or expression.

+++Syntax

```sql
{%= expression != value %}
```

**Example**

The following operation checks if the home address country is not France.

```sql
{%= profile.homeAddress.country != "France" %}
```

+++

### greater than {#greaterthan}

Use the `>` (greater than) function to check if the first value is greater than the second value.

+++Syntax

```sql
{%= expression1 > expression2 %}
```

**Example**

The following operation defines people born strictly after 1970.

```sql
{%= profile.person.birthYear > 1970 %}
```

+++

### greater than or equal to {#greaterthanorequal}

Use the `>=` (greater than or equal to) function to check if the first value is greater than or equal to the second value.

+++Syntax

```sql
{%= expression1 >= expression2 %}
```

**Example**

The following operation defines people born in or after 1970.

```sql
{%= profile.person.birthYear >= 1970 %}
```

+++

### less than {#lessthan}

Use the `<` (less than) comparison function to check if the first value is less than the second value.

+++Syntax

```sql
{%= expression1 < expression2 %}
```

**Example**

The following operation defines people born before 2000.

```sql
{%= profile.person.birthYear < 2000 %}
```

+++

### less than or equal to{#lessthanorequal}

Use the `<=` (less than or equal to) comparison function to check if the first value is less than or equal to the second value.

+++Syntax

```sql
{%= expression1 <= expression2 %}
```

**Example**

The following operation defines people born in 2000 or before.

```sql
{%= profile.person.birthYear <= 2000 %}
```

+++

## Dynamic functions {#dynamic-helpers}

Use the dynamic helper functions to use conditional evaluations, iteration, and variable assignments for dynamic personalization.

### Default Fallback Value {#default-value}

The `Default Fallback Value` helper is used to return a default fallback value if an attribute is empty or null. This mechanism works for Profile attributes and Journey events.

+++Syntax

```sql
Hello {%=profile.personalEmail.name.firstName ?: "there" %}!
```

In this example, the value `there` is displayed if the `firstName` attribute of this profile is empty or null.

+++

### Conditions {#if-function}

The `if` helper is used to define a conditional block.
If the expression evaluation returns true, the block is rendered otherwise it is skipped.

+++Syntax

```sql
{%#if contains(profile.personalEmail.address, ".edu")%}
<a href="https://www.adobe.com/academia">Check out this link</a>
```

Following the `if` helper, you can enter an `else` statement to specify a block of code to be executed, if the same condition is false.
The `elseif` statement specifies a new condition to test if the first statement returns false.


**Format**

```sql
{
    {
        {%#if condition1%} element_1 
        {%else if condition2%} element_2 
        {%else%} default_element 
        {%/if%}
    }
}
```
<!-- 
**Examples**

* **Render different store links based on conditional expressions**

    ```sql
    {%#if profile.homeAddress.countryCode = "FR"%}
    <a href="https://www.somedomain.com/fr">Consultez notre catalogue</a>
    {%else%}
    <a href="https://www.somedomain.com/en">Checkout our catalogue</a>
    {%/if%}
    ```

* **Determine email address extension**

    ```sql
    {%#if contains(profile.personalEmail.address, ".edu")%}
    <a href="https://www.adobe.com/academia">Checkout our page for Academia personals</a>
    {%else if contains(profile.personalEmail.address, ".org")%}
    <a href="https://www.adobe.com/orgs">Checkout our page for Non Profits</a>
    {%else%}
    <a href="https://www.adobe.com/users">Checkout our page</a>
    {%/if%}
    ```

* **Add a conditional link**

    The following operation adds a link to the `www.adobe.com/academia` website for profiles with '.edu' email addresses only, the `www.adobe.com/org` website for profiles with '.org' email addresses, and the default URL `www.adobe.com/users` for all other profiles:

    ```sql
    {%#if contains(profile.personalEmail.address, ".edu")%}
    <a href="https://www.adobe.com/academia">Checkout our page for Academia personals</a>
    {%else if contains(profile.personalEmail.address, ".org")%}
    <a href="https://www.adobe.com/orgs">Checkout our page for Non Profits</a>
    {%else%}
    <a href="https://www.adobe.com/users">Checkout our page</a>
    {%/if%}
    ```

* **Conditional content based on audience membership**

    ```sql
    {%#if profile.segmentMembership.get("ups").get("5fd513d7-d6cf-4ea2-856a-585150041a8b").status = "existing"%}
    Hi! Esteemed gold member. <a href="https://www.somedomain.com/gold">Checkout your exclusive perks </a>
    {%else if profile.segmentMembership.get("ups").get("5fd513d7-d6cf-4ea2-856a-585150041a8c").status = "existing"%}
    Hi! Esteemed silver member. <a href="https://www.somedomain.com/silver">Checkout your exclusive perks </a>
    {%/if%}
    ```
-->

+++

### Unless {#unless}

Use the `Unless` helper is to define a conditional block. By opposition to the `if`  helper, if the expression evaluation returns false, the block is rendered.

+++Syntax

```sql
{%#unless unlessCondition%} element_1 {%else%} default_element {%/unless%}
```

**Example**

Render some content based on the email address extension:

```sql
{%#unless endsWith(profile.personalEmail.address, ".edu")%}
Some Normal Content
{%else%}
Some edu specific content
{%/unless%}
```

+++

### Each {#each}

Use the `each` helper to iterate over an array.

The helper structure is ```{{#each ArrayName}}``` YourContent `{{/each}}` 

You can use the keyword `this` inside the block  to refer to the individual array items. Use `{{@index}}` to render the index of the array's element. 

+++Syntax

```sql
{{#each profile.productsInCart}}
    <li>{{this.name}}</li>
{{/each}}
```

**Example**

```sql
{{#each profile.homeAddress.city}}
  {{@index}} : {{this}}<br>
{{/each}}
```

**Example**

Render a list of products that this user has in their cart:

```sql
{{#each profile.products as |product|}}
    <li>{{product.productName}} {{product.productRating}}</li>
{{/each}}
```

+++

### with {#with}

Use the `with` helper to change the evaluation token of template-part.

+++Syntax

```sql
{{#with profile.person.name}}
{{this.firstName}} {{this.lastName}}
{{/with}}
```

The `with` helper is useful to define a shortcut variable too.

**Example**

Use `with` for aliasing long variable names to shorter ones:

```sql
{{#with profile.person.name as |name|}}
 Hi {{name.firstName}} {{name.lastName}}!
 Checkout our trending products for today!
{{/with}}
```

+++

### let {#let}

The `let` function allows an expression to be stored as a variable to be used later in a query.

+++Syntax

```sql
{% let variable = expression %} {{variable}}
```

**Example**

The following example lets you calculate the total sum of prices for products in the cart with prices between 100 and 1000.

```sql
{% let sum = 0%}
    {{#each profile.productsInCart as |p|}}
        {%#if p.price>100 and p.price<1000%}
            {%let sum = sum + p.price %}
        {%/if%}
    {{/each}}
{{sum}}
```

+++

## Execution metadata {#execution-metadata}

>[!AVAILABILITY]
>
>This capability is in Limited Availability. Contact your Adobe representative to gain access.

Use the `executionMetadata` to  capture and store custom key-value pairs dynamically into the message execution context.

With this function, you can append contextual information to any native action from your campaigns or journeys. Use it to export real-time delivery contextual data to external systems for various purposes, such as tracking, analytics, personalization and downstream processing.

>[!NOTE]
>
>Custom actions do not support the `executionMetadata` function.

For example, you can use the `executionMetadata` helper to append a specific ID to each delivery sent to each profile. This information is generated during runtime and the enriched execution metadata can then be exported for downstream reconciliation with an external reporting platform.

+++Syntax

```
{{executionMetadata key="your_key" value="your_value"}}
```

In this syntax, `key` refers to the metadata name and `value` is the metadata to persist.

**How it works**

Select any element from your channel content inside a campaign or a journey and, using the personalization editor, add the `executionMetadata` helper to this element. 

>[!NOTE]
>
>The `executionMetadata` function is not visible when the content itself is displayed.


At runtime, the metadata value is added to the existing **[!UICONTROL Message Feedback Event Dataset]** with the following schema addition:

```
"_experience": {
  "customerJourneyManagement": {
    "messageExecution": {
      "metadata": {
        "your_key": "your_value"
      }
    }
  }
}
```

>[!IMPORTANT]
>
>There is an upper limit of 2kb on the key value pairs per action. If the 2Kb limit is exceeded, the message is still delivered, but any of the key value pairs can be truncated.

**Example**

```
{{executionMetadata key="firstName" value=profile.person.name.firstName}}
```

In this example, assuming `profile.person.name.firstName` = "Alex", the resulting entity is:

```
{
  "key": "firstName",
  "value": "Alex"
}
```

+++

## Map functions {#maps}

Use map functions in personalization to make interaction with maps easier. 

### get {#get}

Use the `get` function to retrieve the value of a map for a given key.

+++Syntax

```sql
{%= get(map, string) %}
```

**Example**

The following operation gets the value of the identity map for the key `example@example.com`.

```sql
{%= get(identityMap,"example@example.com") %}
```

+++

### keys {#keys}

Use the `keys` function to retrieve all the keys for a given map.

+++Syntax

```sql
{%= keys(map) %}
```

**Example**

The following operation retrieves all the keys for the map `identityMap`.

```sql
{%= keys(identityMap) %}
```

+++

### values {#values}

The `values` function is used to retrieve all the values of a given map.

+++Syntax

```sql
{%= values(map) %}
```

**Example**

The following operation retrieves all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```

+++

## Math functions {#math}

Learn how to use Math functions in the personalization editor.

### absolute {#absolute}

Use the `absolute` function to convert a number to its absolute value.

+++Syntax

```sql
{%= absolute(int) %}: int
```

+++

### formatNumber {#format-number}

Use the `formatNumber` function to format any number into its language-sensitive representation.

It accepts a number and a string representing the locale, and returns a formatted string of the number in the desired locale.

+++Syntax

```sql
{%= formatNumber(number/double,string) %}: string
```

You can use formatting and valid locales as summarized in the [Oracle documentation](https://docs.oracle.com/javase/8/docs/api/java/util/Locale.html) and [Supported locales](https://www.oracle.com/java/technologies/javase/jdk11-suported-locales.html){_blank}

**Example**

This query returns a formatted string in Arabic corresponding to 123456.789 as the input number.

```sql
{%= formatNumber(123456.789, "ar_EG") %}
```

+++

### random {#random}

Use the `random` function to return a random value between 0 and 1.

+++Syntax

```sql
{%= random() %}: double
```

+++

## roundDown {#round-down}

Use the `roundDown` function to round a number down.

+++Syntax

```sql
{%= roundDown(double) %}: double
```

+++

### roundUp {#round-up}

Use the `roundUp` function to round a number up.

+++Syntax

```sql
{%= roundUp(double) %}: double
```

+++

### toHexString {#to-hex-string}

The `toHexString` function converts any number into its hexadecimal string.

+++Syntax

```sql
{%= toHexString(number) %}: string
```

**Example**

This query returns the hexadecimal value of 158 as 9e.

```sql
{%= toHexString(158) %}
```

+++

### toInt {#to-int}

Use the `toInt` function to convert types (number, double, integer, long, float, short, byte, boolean, string) to an integer.

+++Syntax

```sql
{%= toInt(<valueToConvert>) %}: integer
```

**Example**

This query returns the integer value of 42.6 as 42.

```sql
{%= toInt(42.6) %}: integer
```

+++

### toPercentage {#to-percentage}

Use the `toPercentage` function to convert a number to percentage.

+++Syntax

```sql
{%= toPercentage(double) %}: string
```

+++

### ToPrecision {#to-precision}

Use the `toPrecision` function to convert a number to required precision.

+++Syntax

```sql
{%= toPrecision(double,int) %}: string
```

+++

## toString {#to-string}

The **toString** function converts any number into its string representation. 

+++Syntax

```sql
{%= toString(string) %}: string
```

**Example**

This query returns `"12"`.

```sql
{%= toString(12) %} 
```

+++

## Object functions {#objects}

Object functions to query object properties or attributes. 

### isNull {#isNull}

The `isNull` function determines if an object reference does not exist.

+++Syntax

```sql
{%= isNull(object) %}
```

**Example**

The following operation checks if the person's home address does not exist.

```sql
{%= isNull(person.homeAddress) %}
```

+++

## isNotNull {#isNotNull}

The `isNotNull` function determines if an object reference exists.

+++Syntax

```sql
{%= isNotNull(object) %}
```

**Example**

The following operation checks if the person's home address exists.

```sql
{%= isNotNull(person.homeAddress) %}
```

+++

## String functions {#string-functions}

Learn how to use String functions in the personalization editor.

### camelCase {#camelCase}

The `camelCase` function capitalizes the first letter of each word of a string.

+++Syntax

```sql
{%= camelCase(string)%}
```

**Example**

The following function capitalizes the first letter of a word in the profile's street address.

```sql
{%= camelCase(profile.homeAddress.street) %}
```

+++

### charCodeAt {#char-code-at}

The `charCodeAt` function returns ASCII value of a character, like the `charCodeAt` function in JavaScript. It takes a string and an integer (defining the position of a character) as input arguments and returns its corresponding ASCII value.

+++Syntax

```sql
{%= charCodeAt(string,int) %}: int
```

**Example**

The following function returns the ASCII value of `o` (111).

```sql
{%= charCodeAt("some", 1)%}
```

+++

### concat {#concate}

The `concat` function combines two strings into one.

+++Syntax

```sql
{%= concat(string,string) %}
```

**Example**

The following function combines profile city and country in a single string.

```sql
{%= concat(profile.homeAddress.city,profile.homeAddress.country) %}
```

+++

### contains {#contains}

Use the `contains` function to determine if a string contains a specified substring.

+++Syntax

```sql
{%= contains(STRING_1, STRING_2, CASE_SENSITIVE) %}
```

| Argument | Description |
| --------- | ----------- |
| `STRING_1` | The string to perform the check on. |
| `STRING_2` | The string to search for within the first string. |
| `CASE_SENSITIVE` | An optional parameter to determine if the check is case sensitive. Possible values: true (default) / false. |

**Examples**

* The following function checks if the profile first name contains the letter A (in upper or lower case). If the profile does, it returns `true`. If not, it returns `false`.

    ```sql
    {%= contains(profile.person.name.firstName, "A", false) %}
    ```

* The following query determines, with case sensitivity, if the person's email address contains the string `2010@gm`.

    ```sql
    {%= contains(profile.person.emailAddress,"2010@gm") %}
    ```

+++

### doesNotContain {#doesNotContain}

Use the `doesNotContain` function to determine if a string does not contain a specified substring.

+++Syntax

```sql
{%= doesNotContain(STRING_1, STRING_2, CASE_SENSITIVE)%}
```

| Argument | Description |
| --------- | ----------- |
| `STRING_1` | The string to perform the check on. |
| `STRING_2` | The string to search for within the first string. |
| `CASE_SENSITIVE` | An optional parameter to determine if the check is case sensitive. Possible values: true (default) / false. |

**Example**

The following query determines, with case sensitivity, if the person's email address does not contain the string `2010@gm`.

```sql
{%= doesNotContain(profile.person.emailAddress,"2010@gm")%}
```

+++

### doesNotEndWith {#doesNotEndWith}

Use the `doesNotEndWith` function to determine if a string does not end with a specified substring.

+++Syntax

```sql
{%= doesNotEndWith(STRING_1, STRING_2, CASE_SENSITIVE)%}
```

| Argument | Description |
| --------- | ----------- |
| `{STRING_1}` | The string to perform the check on. |
| `{STRING_2}` | The string to search for within the first string. |
| `{CASE_SENSITIVE}` | An optional parameter to determine if the check is case sensitive. Possible values: true (default) / false. |

**Example**

The following query determines, with case sensitivity, if the person's email address does not end with `.com`.

```sql
doesNotEndWith(person.emailAddress,".com")
```

+++

### doesNotStartWith {#doesNotStartWith}

Use the `doesNotStartWith` function to determine if a string does not start with a specified substring.

+++Syntax

```sql
{%= doesNotStartWith(STRING_1, STRING_2, CASE_SENSITIVE)%}
```

| Argument | Description |
| --------- | ----------- |
| `{STRING_1}` | The string to perform the check on. |
| `{STRING_2}` | The string to search for within the first string. |
| `{CASE_SENSITIVE}` | An optional parameter to determine if the check is case sensitive. Possible values: true (default) / false. |

**Example**

The following query determines, with case sensitivity, if the person's name does not start with `Joe`.

```sql
{%= doesNotStartWith(person.name,"Joe")%}
```

+++

### encode64 {#encode64}

Use the `encode64` function to encode a string to preserve Personal Information (PI), such as to be included in a URL.

+++Syntax

```sql
{%= encode64(string) %}
```

+++

### endsWith {#endsWith}

Use the `endsWith` function to determine if a string ends with a specified substring.

+++Syntax

```sql
{%= endsWith(STRING_1, STRING_2, CASE_SENSITIVE) %}
```

| Argument | Description |
| --------- | ----------- |
| `{STRING_1}` | The string to perform the check on. |
| `{STRING_2}` | The string to search for within the first string. |
| `{CASE_SENSITIVE}` | An optional parameter to determine if the check is case sensitive. Possible values: true (default) / false.  |

**Example**

The following query determines, with case sensitivity, if the person's email address ends with `.com`.

```sql
{%= endsWith(person.emailAddress,".com") %}
```

+++

### equals {#equals}

Use the `equals` function to determine if a string is equal to the specified string, with case sensitivity.

+++Syntax

```sql
{%= equals(STRING_1, STRING_2) %}
```

| Argument | Description |
| --------- | ----------- |
| `{STRING_1}` | The string to perform the check on. |
| `{STRING_2}` | The string to compare with the first string. |

**Example**

The following query determines, with case sensitivity, if the person's name is `John`.

```sql
{%=equals(profile.person.name,"John") %}

```

+++

### equalsIgnoreCase {#equalsIgnoreCase}

Use the `equalsIgnoreCase` function to determine if a string is equal to the specified string, without case sensitivity.

+++Syntax

```sql
{%= equalsIgnoreCase(STRING_1, STRING_2) %}
```

| Argument | Description |
| --------- | ----------- |
| `{STRING_1}` | The string to perform the check on. |
| `{STRING_2}` | The string to compare with the first string. |

**Example**

The following query determines, without case sensitivity, if the person's name is `John`.

```sql
{%= equalsIgnoreCase(profile.person.name,"John") %}

```

+++

### extractEmailDomain {#extractEmailDomain}

Use the `extractEmailDomain` function to extract the domain of an email address.

+++Syntax

```sql
{%= extractEmailDomain(string) %}
```

**Example**

The following query extracts the email domain of the personal email address.

```sql
{%= extractEmailDomain(profile.personalEmail.address) %}
```

+++

### formatCurrency {#format-currency}

Use the `formatCurrency` function to convert any number into its corresponding language-sensitive currency representation depending on the locale passed as a string in the second argument.

+++Syntax

```sql
{%= formatCurrency(number/double,string) %}: string
```

**Example**

This query returns £56.00

```sql
{%= formatCurrency(56L,"en_GB") %}
```

+++

### getUrlHost {#get-url-host}

Use the `getUrlHost` function to retrieve the hostname of a URL.

+++Syntax

```sql
{%= getUrlHost(string) %}: string
```

**Example**

```sql
{%= getUrlHost("https://www.myurl.com/contact") %}
```

Returns "www.myurl.com"

+++

### getUrlPath {#get-url-path}

Use the `getUrlPath` function to retrieve the path after the domain name of a URL.

+++Syntax

```sql
{%= getUrlPath(string) %}: string

```

**Example**

```sql
{%= getUrlPath("https://www.myurl.com/contact.html") %}
```

Returns "/contact.html"

+++

### getUrlProtocol {#get-url-protocol}

Use the `getUrlProtocol` function to retrieve the protocol of a URL.

+++Syntax

```sql
{%= getUrlProtocol(string) %}: string
```

**Example**

```sql
{%= getUrlProtocol("https://www.myurl.com/contact.html") %}
```

Returns "http"

+++

### indexOf {#index-of}

Use the `indexOf` function to return the position (in the first argument) of the first occurrence of the second parameter. Returns -1 if there is no match.

+++Syntax

```sql
{%= indexOf(STRING_1, STRING_2) %}: integer
```

| Argument | Description |
| --------- | ----------- |
| `{STRING_1}` | The string to perform the check on. |
| `{STRING_2}` | The string to search in the first parameter|

**Example**

```sql
{%= indexOf("hello world","world" ) %}
```

Returns 6.

+++

### isEmpty {#isEmpty}

Use the `isEmpty` function to determine if a string is empty.

+++Syntax

```sql
{%= isEmpty(string) %}
```

**Example**

The following function returns 'true' if the profile's mobile phone number is empty. Else, it returns `false`.

```sql
{%= isEmpty(profile.mobilePhone.number) %}
```

+++

### isNotEmpty {#is-not-empty}

Use the `isNotEmpty` function to determine if a string is not empty.

+++Syntax

```sql
{= isNotEmpty(string) %}: boolean
```

**Example**

The following function returns 'true' if the profile's mobile phone number is not empty. Else, it returns `false`.

```sql
{%= isNotEmpty(profile.mobilePhone.number) %}
```

+++

### lastIndexOf {#last-index-of}

Use the `lastIndexOf` function to return the position (in the first argument) of the last occurrence of the second parameter. Returns -1 if there is no match.

+++Syntax

```sql
{= lastIndexOf(STRING_1, STRING_2) %}: integer
```

| Argument | Description |
| --------- | ----------- |
| `{STRING_1}` | The string to perform the check on. |
| `{STRING_2}` | The string to search in the first parameter|

**Example**

```sql
{%= lastIndexOf("hello world","o" ) %}
```

Returns 7.

+++

### leftTrim {#leftTrim}

Use the `leftTrim` function to remove white spaces from beginning of a string.

+++Syntax

```sql
{%= leftTrim(string) %}
```

+++

### length {#length}

Use the `length` function to get the number of characters in a string or an expression.

+++Syntax

```sql
{%= length(string) %}
```

**Example**

The following function returns the length of the profile's city name.

```sql
{%= length(profile.homeAddress.city) %}
```

+++

### like {#like}

Use the `like` function to determine if a string matches a specified pattern.

+++Syntax

```sql
{%= like(STRING_1, STRING_2) %}
```

| Argument | Description |
| --------- | ----------- |
| `{STRING_1}` | The string to perform the check on. |
| `{STRING_2}` | The expression to match against the first string. There are two supported special characters for creating an expression: `%` and `_`. <ul><li>`%` is used to represent zero or more characters.</li><li>`_` is used to represent exactly one character.</li></ul> |

**Example**

The following query retrieves all the cities where profiles live containing the pattern `es`.

```sql
{%= like(profile.homeAddress.city, "%es%")%}
```

+++

### lowerCase {#lower}

Use the `lowerCase` function to convert a string to lower case letters.

+++Syntax

```sql
{%= lowerCase(string) %}
```

**Example**

This function converts the profile first name to lower case letters.

```sql
{%= lowerCase(profile.person.name.firstName) %}
```

+++

### matches {#matches}

Use the `matches` function  to determine if a string matches a specific regular expression. For more information about matching patterns in regular expressions, refer to [the Oracle documentation](https://docs.oracle.com/javase/8/docs/api/java/util/regex/Pattern.html).

+++Syntax

```sql
{%= matches(STRING_1, STRING_2) %}
```

**Example**

The following query determines, without case sensitivity, if the person's name starts with `John`.

```sql
{%= matches(person.name.,"(?i)^John") %}
```

+++

### mask {#mask}

Use the `mask` function to replace a part of a string with "X" characters.

+++Syntax

```sql
{%= mask(string,integer,integer) %}
```

**Example**

The following query replaces the "123456789" string with "X" characters, excepted for the first and the last 2 characters.

```sql
{%= mask("123456789",1,2) %}
```

The query returns `1XXXXXX89`.

+++

### md5 {#md5}

Use the `md5` function to calculate and return the md5 hash of a string.

+++Syntax

```sql
{%= md5(string) %}: string
```

**Example**

```sql
{%= md5("hello world") %}
```

Returns "5eb63bbbe01eeed093cb22bb8f5acdc3"

+++

### notEqualTo {#notEqualTo}

Use the `notEqualTo` function to determine if a string is not equal to the specified string.

+++Syntax

```sql
{%= notEqualTo(STRING_1, STRING_2) %}
```

| Argument | Description |
| --------- | ----------- |
| `{STRING_1}` | The string to perform the check on. |
| `{STRING_2}` | The string to compare with the first string. |

**Example**

The following query determines, with case sensitivity, if the person's name is not `John`.

```sql
{%= notEqualTo(profile.person.name,"John") %}
```

+++

### notEqualWithIgnoreCase {#not-equal-with-ignore-case}

Use the `notEqualWithIgnoreCase` function to compare two strings ignoring case.

+++Syntax

```sql
{= notEqualWithIgnoreCase(STRING_1,STRING_2) %}: boolean
```

| Argument | Description |
| --------- | ----------- |
| `{STRING_1}` | The string to perform the check on. |
| `{STRING_2}` | The string to compare with the first string. |

**Example**

The following query determines if the person's name is not `john`, with no case sensitivity.

```sql
{%= notEqualTo(profile.person.name,"john") %}
```

+++

### regexGroup {#regexGroup}

Use the `regexGroup` function to extract specific information, based on the regular expression provided.

+++Syntax

```sql
{%= regexGroup(STRING, EXPRESSION, GROUP) %}
```

| Argument | Description |
| --------- | ----------- |
| `{STRING}` | The string to perform the check on. |
| `{EXPRESSION}` | The regular expression to match against the first string. |
| `{GROUP}` | Expression group to match against. |

**Example**

The following query extracts the domain name from an email address.

```sql
{%= regexGroup(emailAddress,"@(\\w+)", 1) %}
```

+++

### replace {#replace}

Use the `replace` function to replace a given substring in a string with another substring.

+++Syntax

```sql
{%= replace(STRING_1,STRING_2,STRING_3) %}:string
```

| Argument | Description |
| --------- | ----------- |
| `{STRING_1}` | The string where the substring must be replaced. |
| `{STRING_2}` | The substring to replace. |
| `{STRING_3}` | The replacement substring. |

**Example**

```sql
{%= replace("Hello John, here is your monthly newsletter!","John","Mark") %}
```

Returns `Hello Mark, here is your monthly newsletter!`

+++

### replaceAll {#replaceAll}

Use the `replaceAll` function to replace all substrings of a text that matches the regex expression with the specified literal replacement string. Regex has special handling of `\` and `+` and all regex expressions follow the PQL escaping strategy. The replacement proceeds from the beginning of the string to the end, for example, replacing `aa` with `b` in the string `aaa` results in `ba` rather than `ab`.

+++Syntax

```sql
{%= replaceAll(string,string,string) %}
```

>[!NOTE]
>
> When the expression taken as second argument is a special regex character, use double back-slash (`//`).  Special regex characters are: [., +, *, ?, ^, $, (, ), [, ], {, }, |, \.]
> 
> Learn more in [Oracle documentation](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html){_blank}.
>

+++

### rightTrim {#rightTrim}

The `rightTrim` function removes white spaces from end of a string.

+++Syntax

```sql
{%= rightTrim(string) %}
```

+++

### sha256 {#sha256}

The `sha256` function calculates and returns the sha256 hash of a string.

+++Syntax

```sql

{%= sha256(string) %} : string
```

**Example**

```sql
{%= sha256("Eliechxh")%}
```

Returns `0b0b207880b999adaad6231026abf87caa30760b6f326b21727b61139332257d`

+++

### split {#split}

Use the `split` function to split a string by a given character.

+++Syntax

```sql
{%= split(string,string) %}
```

+++

## startsWith {#startsWith}

Use the `startsWith` function to determine if a string starts with a specified substring.

+++Syntax

```sql
{%= startsWith(STRING_1, STRING_2, CASE_SENSITIVE) %}

```

| Argument | Description |
| --------- | ----------- |
| `{STRING_1}` | The string to perform the check on. |
| `{STRING_2}` | The string to search for within the first string. |
| `{CASE_SENSITIVE}` | An optional parameter to determine if the check is case sensitive. By default, it is set to true. |

**Example**

The following query determines, with case sensitivity, if the person's name starts with `Joe`.

```sql
{%= startsWith(person.name,"Joe") %}
```

+++

### stringToDate {#string-to-date}

The `stringToDate` function converts a string value into a date-time value. It takes two arguments: string representation of a date-time and string representation of the formatter.

+++Syntax

```sql
{= stringToDate("date-time value","formatter" %}
```

**Example**

```sql
{= stringToDate("2023-01-10 23:13:26", "yyyy-MM-dd HH:mm:ss") %}
```

+++

### string_to_integer {#string-to-integer}

Use the `string_to_integer` function to convert a string value into an integer value.

+++Syntax

```sql
{= string_to_integer(string) %}: int
```

+++

### stringToNumber {#string-to-number}

Use the `stringToNumber` function to convert a string into number. It returns the same string as output for invalid input.

+++Syntax

```sql
{%= stringToNumber(string) %}: double
```

+++

### substr {#sub-string}

Use the `substr` function to return the sub-string of the string expression between the beginning index and the ending index.

+++Syntax

```sql
{= substr(string, integer, integer) %}: string
```

+++

### titleCase {#titleCase}

Use the `titleCase` function to capitalize first letters of each words of a string.

+++Syntax

```sql
{%= titleCase(string) %}
```

**Example**

If the person lives in Washington high street, this function returns `Washington High Street`.

```sql
{%= titleCase(profile.person.location.Street) %}
```

+++

### toBool {#to-bool}

Use the `toBool` function to convert an argument value into a boolean value, depending on its type.

+++Syntax

```sql
{= toBool(string) %}: boolean
```

+++

### toDateTime {#to-date-time}

Use the `toDateTime` function to convert string to date. It returns the epoch date as output for invalid input.

+++Syntax

```sql
{%= toDateTime(string, string) %}: date-time
```

+++

### toDateTimeOnly {#to-date-time-only}

Use the `toDateTimeOnly` function to convert an argument value into a date time only value. It returns the epoch date as output for invalid input. This function accepts string, date, long, and integer field types.

+++Syntax

```sql
{%= toDateTimeOnly(string/date/long/int) %}: date-time
```

+++

### trim {#trim}

The `trim` function removes all white spaces from the beginning and at the end of a string.

+++Syntax

```sql
{%= trim(string) %}
```

+++

### upperCase {#upper}

The `upperCase` function converts a string to upper case letters.

+++Syntax

```sql
{%= upperCase(string) %}
```

**Example**

This function converts the profile last name to upper case letters.

```sql
{%= upperCase(profile.person.name.lastName) %}
```

+++

### urlDecode {#url-decode}

Use the `urlDecode` function to decode a url encoded string.

+++Syntax

```sql
{%= urlDecode(string) %}: string
```

+++

### urlEncode {#url-encode}

Use the `urlEncode` function to encode a string as a URL.

+++Syntax

```sql
{%= urlEncode(string) %}: string
```

+++
