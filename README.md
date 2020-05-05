# AnyGrids
AnyGrids - Free JavaScript tool for visualizing any business data :v:

![npm](https://img.shields.io/npm/dw/anygrids) ![npm bundle size](https://img.shields.io/bundlephobia/min/anygrids)

## Resources
* [Live demo](https://anygrids.com)
* [twitter](https://twitter.com/AnyGrids)
## Installation and usage
Start by installing AnyGrids as a node module and save it as a dependency in your package.json:
```
npm install anygrids --save
```
Then, include the JS file from node_modules:
```html
<script src="node_modules/anygrids/anygrids.js"></script>
```

Or via unpkg.com:
```html
<script src="https://unpkg.com/anygrids@latest/anygrids.js"></script>
```

Now, you can create an instance of AnyGrids table:
```html
<div id="anygrids">The component will appear here</div>
<script>
    //JSON data example:
    const data = [
        {
            id: 1,
            email: "michael.lawson@mail.in",
            first_name: "Michael",
            last_name: "Lawson",
            avatar: "https://s3.amazonaws.com/uifaces/faces/twitter/follettkyle/128.jpg",
            linear: [0, 30, 5, 29, 34],
            bar: [0, 30, 5, 29, 34],
            pie: [0.25, 0.30, 0.45],
            orders: 5,
        },
        {
            id: 2,
            email: "lindsay.ferguson@mail.in",
            first_name: "Lindsay",
            last_name: "Ferguson",
            avatar: "https://s3.amazonaws.com/uifaces/faces/twitter/araa3185/128.jpg",
            linear: [0, 30, 5, 29, 34],
            bar: [0, 30, 5, 29, 34],
            pie: [0.25, 0.30, 0.45],
            orders: 25,
        },
        {
            id: 3,
            email: "michael.lawson@mail.in",
            first_name: "Michael",
            last_name: "Lawson",
            avatar: "https://s3.amazonaws.com/uifaces/faces/twitter/follettkyle/128.jpg",
            linear: [0, 30, 5, 29, 34],
            bar: [0, 30, 5, 29, 34],
            pie: [0.25, 0.30, 0.45],
            orders: 5,
        },
        {
            id: 4,
            email: "lindsay.ferguson@mail.in",
            first_name: "Lindsay",
            last_name: "Ferguson",
            avatar: "https://s3.amazonaws.com/uifaces/faces/twitter/araa3185/128.jpg",
            linear: [0, 30, 5, 29, 34],
            bar: [0, 30, 5, 29, 34],
            pie: [0.25, 0.30, 0.45],
            orders: 25,
        }
    ];

    document.addEventListener("DOMContentLoaded", function() {
        new AnyGrids({
            container: 'anygrids', //div id
            data, //JSON data
            pagination: {
                perPage: 2
            },
            rows: {
                child: {
                    template: '<div><img src="avatar"> <div style="display:flex;">first_name last_name</div></div>pie_render'
                }
            },
            columns: [
                {field: 'id', title: '', type: 'string', width: 30, sortable: true},
                {field: 'email', title: 'E-mail', type: 'string', width: 200},
                {field: 'first_name', title: 'First name', type: 'string', width: 200, sortable: true},
                {field: 'last_name', title: 'Last name', type: 'string', width: 100, sortable: true},
                {field: 'avatar', title: 'Avatar', type: 'image', width: 50, class: 'avatar'},
                {field: 'linear', title: 'Linear', type: 'sparklines-linear', width: 150},
                {field: 'bar', title: 'Bar', type: 'sparklines-bar', width: 150},
                {field: 'pie', title: 'Pie', type: 'sparklines-pie', width: 150},
                {field: 'orders', title: 'Orders', type: 'number', width: 150, total: {show: true, label: 'Total orders: '}},
            ]
        })
    });

</script> 
```
