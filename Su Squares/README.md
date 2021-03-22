# Su Squares Attributes

This project generates a CSV file listing interesting attributes for Su Squares.

## Data definitions

Immutable definitions (these attribute values will never change):

* `X_POSITION`—The horizontal position of the square, 1 is leftmost and 100 is rightmost
* `Y_POSITION`—The vertical position of the square, 1 is at top and 100 is at bottom
* `DISTANCE_TO_EDGE`—How many squares distance to the nearest edge (zero if this is an edge square)
* `DISTANCE_TO_CENTER`—How many squares (Manhattan) distance to the nearest center (zero for each of the four center squares)

Mutable definitions (these attributes will change based on various conditions):

* `DISTANCE_TO_SOLD`—The (Manhattan) distance to the nearest square which has been sold (zero for a square that has been sold)
  * This number will change (always decreasing) as more squares are sold, and will eventually become zero for all squares.
* `NTH_RECENT_PERSONALIZATION`—The most recent square that was personalized is 1, the next recent is 2, etc. (Squares that have never been personalized are `NULL`)
  * This will update when squares are personalized.

Market definitions (these attributes will change based on transactions):

* `LAST_SALE_PRICE_USD`—The last sale price for this square that was recorded on any trading platform  as priced in US dollars (using the then-current exchange rate)
* `LAST_SALE_TIME`—The last sale time (seconds since Unix Epoch) that was record on any trading platform