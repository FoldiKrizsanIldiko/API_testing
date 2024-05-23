POST {{BASE_URL}}/orders

![alt text](image-1.png)


body:
{
  "bookId": {{NFABook0id}},
  "customerName": "{{$randomFullName}}"
}


test:
pm.test("Status code is 201", function () {
    pm.response.to.have.status(201);
});

const orderID = pm.response.json().orderId
console.log(orderID)

pm.globals.set("orderId", orderID);


