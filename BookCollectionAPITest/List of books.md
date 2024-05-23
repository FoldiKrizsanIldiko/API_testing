GET {{BASE_URL}}/books

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

const books= pm.response.json();
const nonFictionAvailableBooks = books.filter((book)=> book.type == "non-fiction" && book.available == true);
console.log(nonFictionAvailableBooks.length);
if(nonFictionAvailableBooks){
    for(let i=0;i<nonFictionAvailableBooks.length;i++){
        pm.globals.set(`NFABook${i}id`, nonFictionAvailableBooks[i].id);
    }
}
pm.test("",()=>{
    pm.expect(nonFictionAvailableBooks[0].available).to.be.true;
    pm.expect(nonFictionAvailableBooks[0].type).to.eql("non-fiction");
    pm.expect(pm.response.responseTime).to.be.below(400);
})

response: 
[
    {
        "id": 1,
        "name": "The Russian",
        "type": "fiction",
        "available": true
    },
    {
        "id": 2,
        "name": "Just as I Am",
        "type": "non-fiction",
        "available": false
    },
    {
        "id": 3,
        "name": "The Vanishing Half",
        "type": "fiction",
        "available": true
    },
    {
        "id": 4,
        "name": "The Midnight Library",
        "type": "fiction",
        "available": true
    },
    {
        "id": 5,
        "name": "Untamed",
        "type": "non-fiction",
        "available": true
    },
    {
        "id": 6,
        "name": "Viscount Who Loved Me",
        "type": "fiction",
        "available": true
    }
]