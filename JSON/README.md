# Student Marks System (JSON Example)

- Parsing JSON strings into JavaScript objects.
- Calculating total and average marks for each student.
- Understanding **shallow copy** vs **deep copy**.
- Stringifying JavaScript objects back to JSON.

---

## Features

1. **Parse JSON Data**
   - Simulated API response stored as a JSON string.
   - Converted to JavaScript object using `JSON.parse()`.

2. **Calculate Total and Average Marks**
   - Loop through each student.
   - Sum all marks using `Array.reduce()`.
   - Calculate average marks and format to 2 decimal places.

3. **Shallow Copy Example**
   - Use spread operator `{ ...obj }` to create a shallow copy.
   - Demonstrates that changing nested objects affects the original object.

4. **Deep Copy Example**
   - Use `JSON.stringify()` + `JSON.parse()` to create a deep copy.
   - Changing nested objects in deep copy **does not affect the original**.

5. **Stringify Back to JSON**
   - Convert JavaScript objects back to JSON string using `JSON.stringify()`.
   - Useful for sending data to server or saving in storage.


## Code Snippets

### Parsing JSON

```javascript
const data = JSON.parse(jsonResponse);
Calculating Total & Average
for (let student in data.students) {
  const marks = data.students[student].marks;
  const total = marks.reduce((sum, mark) => sum + mark, 0);
  const average = total / marks.length;
}

Shallow Copy
const shallowCopy = { ...data.students };
shallowCopy.Alice.marks[0] = 0; // affects original

Deep Copy
const deepCopy = JSON.parse(JSON.stringify(data.students));
deepCopy.Bob.marks[0] = 100; // original unaffected

Stringify Back to JSON
const jsonString = JSON.stringify(data.students);

Output Example
Alice → Total: 240, Average: 80.00
Bob → Total: 180, Average: 60.00
Charlie → Total: 270, Average: 90.00

After shallow copy change:
Original Alice marks: 0, 90, 70

After deep copy change:
Original Bob marks: 60, 55, 65

Stringified JSON:
{"Alice":{"marks":[0,90,70]},"Bob":{"marks":[60,55,65]},"Charlie":{"marks":[95,85,90]}}

