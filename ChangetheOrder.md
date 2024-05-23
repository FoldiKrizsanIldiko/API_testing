PATCH {{BASE_URL}}/orders/:orderId

body:
{
  "customerName": "John Wick"
}


test:
 pm.test("Status code is 204", function () {
    pm.response.to.have.status(204);
});

