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

### HTML FETCH IMPLEMENTATION

Get and display data from this test API is very simple! 😊

In your html page, insert a script.
Inside this:
- declare a variable with the test api link:
```markdown
`const url = 'https://daniepa.github.io/testJsonAPI/myData.json';`
```

- use asynchronous fetch api to get data from url:
```markdown
fetch(url)
  .then(res => res.json())
  .then(data => {
    console.log(data);
  });
```

- save html and javascript file;
- open html page, press F12 to enter in developer tools;
- in Concole youy can see the content of 'data' response.





Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
