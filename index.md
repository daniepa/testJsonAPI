## Test .json API 

Go to [API test link](https://daniepa.github.io/testJsonAPI/myData.json) to call my API.

The result is an array of objects (example of products) with some fields (id, code, description. etc).
Yoc can use this API for test.

### Documentation

**GET ALL PRODUCTS**

This is the link to get all product: 
```markdown
https://daniepa.github.io/testJsonAPI/myData.json
```
The array contains five object.

Each object contains this properties:
- "id" (number)
- "code" (string)
- "product_description" (string)
- "categories" (array of strings)
- "quantity" (number)
- "cost" (decimal number)
- "img" (actually it's just an empty string)

### Display data in html file

Get and display data from this test API is very simple! 😊

In your html page, insert a script.
Inside this:
- declare a variable with the test api link:
```markdown
const url = 'https://daniepa.github.io/testJsonAPI/myData.json';
```

- use asynchronous fetch api to get data from url:
```markdown
fetch(url)
  .then(res => res.json())
  .then(data => {
    console.log(data);
  });
```
![Image](src)

- save html and javascript file;
- open html page, press F12 to enter in developer tools;
- in Console tab youy can see the content of 'data' response.

Next steps:
- inside meta tag of your .html, add scrips and link for _jquery_ and _bootstrap_ 5:
```markdown
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.2/dist/css/bootstrap.min.css" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.2/dist/js/bootstrap.bundle.min.js"></script>
```

- inside body tag, create _bootstrap_ container and iside this create a row with an id:
```markdown
    <div class="container pt-5">
        <h1>List of products</h1>
        <div class="row" id="content">
            <!-- qui metto il contenuto del json con js -->
        </div>


    </div>
```

- inside the script create the _jquery_ ready function. Place all javascript content here:
```markdown
    $(document).ready(function () {
      ...
    });
```

- inside the script create the _jquery_ ready function. Place all javascript content here:
```markdown
    $(document).ready(function () {
    
      const url = 'https://daniepa.github.io/testJsonAPI/myData.json';
      
      fetch(url)
        .then(res => res.json())
        .then(data => {
          console.log(data);
      });
  
    });
```

- now comment console.log and replace with for cycle: we want to cycle all data object:
```markdown
    for (let i = 0; i < json.length; i++) {
    
    }
```

- finally append paragraphs with data fields of our objects (I append to #content):
```markdown
    for (let i = 0; i < json.length; i++) {
      $('#content').append(`
         <p>` + json[i].code + `</p>
         <p>` + json[i].product_description + `</p>
         <p>` + json[i].quantity + `</p>
         ...
         <hr>
      `)
    }
```

- with _bootstrap_ you can improve data display: for example you can display data in _bootstrap_ cards instead of the banal paragraphs:
![Image](src)


### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
