## Airplane booking system
Our company needs to add an airplane booking system to the current application.
Currently the fleet is composed only by a short range plane that has the following characteristics:

```js 
{
	"aircraft_type": "short_range",
	"sits_count": 156,
	"rows": 26,
	"row_arrangement": "A B C _ D E F"
}
```

### Requirements:
Create a REST API that supports a multiple-seat booking, expecting the passenger's name and the number of seats to book (up to 7). As a result, it should return the positions of all seats reserved.

#### Constraints:
- If passengers can all fit in a row, the system will book them in the same row. (ex. ['A1', 'B1', 'C1'] or ['E1', 'F1'])

- If passengers don't fit in a row without crossing the aisle, the system will balance them across rows. (ex. ['A1', 'B1', 'A2', 'B2'])

- If there are no available seats and the seats cannot be arranged all across rows, they will be booked to be nearby across the aisle. (ex. ['C1', 'D1', 'C2', 'D2'])

- If none of the above rules are appliable, the system will position passengers in a random seat.

- The booking should start from the window seats, when possible.

#### *Example:*

Bookings:
  * Marco: 4 people;
  * Gerard: 2 people;
Result:
  * Marco seats: 'A1', 'B1', 'A2', 'B2';
  * Gerard seats: 'E1', 'F1'; 

Bookings:
  * Iosu: 2 people;
  * Oriol: 5 people;
  * David: 2 people;
Result:
  * Iosu seats: 'A1', 'B1';
  * Oriol seats: 'D1', 'E1', 'F1', 'E2', 'F2';
  * David seats: 'A2', 'B2';

Bookings:
  * Iosu: 2 people;
  * Gerard: 2 people;
Result:
  * Iosu seats: 'A1', 'B1';
  * Gerard seats: 'E1', 'F1';

### You should:
- Add information about your design decision.
- Write a production-ready code.
- Design the code to be extensible.
- Suggest possible enhancements.
- Provide the source code with all the git history and the description of how to execute the code.
- Feel free to use docker to simplify the execution process. 
