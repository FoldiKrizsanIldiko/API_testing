POST {{BASE_URL}}/api-clients/


body:
{
   "clientName": "Learner",
   "clientEmail": "learner1@example.com"
}

test:
pm.test("Status code is 201", function () {
    pm.response.to.have.status(201);
});

