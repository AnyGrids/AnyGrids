# AnyGrids
AnyGrids - Free JavaScript tool for visualizing any business data
## Resources
[Live demo](https://anygrids.com)
## Installation and usage
Start by installing AnyGrids as a node module and save it as a dependency in your package.json:
```
npm install anygrids --save
```
Then, include the JS file:
```html
<script src="node_modules/anygrids/anygrids.js"></script>
```
Now, you can create an instance of AnyGrids table:
```html
<div id="anygrids">The component will appear here</div>
<script>
    //JSON data example:
    const data = [{
            id: 7,
            email: "michael.lawson@mail.in",
            first_name: "Michael",
            last_name: "Lawson",
            avatar: "https://s3.amazonaws.com/uifaces/faces/twitter/follettkyle/128.jpg",
            linear: [0.25, 0.30, 0.45],
            bar: [0.25, 0.30, 0.45],
            pie: [0.25, 0.30, 0.45],
            orders: 5,
        },
        {
            id: 8,
            email: "lindsay.ferguson@mail.in",
            first_name: "Lindsay",
            last_name: "Ferguson",
            avatar: "https://s3.amazonaws.com/uifaces/faces/twitter/araa3185/128.jpg",
            linear: [0.25, 0.30, 0.45],
            bar: [0.25, 0.30, 0.45],
            pie: [0.25, 0.30, 0.45],
            orders: 25,
        }];

    new AnyGrids({
        container: 'anygrids', //div id
        data,
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
</script> 
```
