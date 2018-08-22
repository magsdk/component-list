List component
==============

[![build status](https://img.shields.io/travis/magsdk/component-list.svg?style=flat-square)](https://travis-ci.org/magsdk/component-list)
[![npm version](https://img.shields.io/npm/v/mag-component-list.svg?style=flat-square)](https://www.npmjs.com/package/mag-component-list)
[![dependencies status](https://img.shields.io/david/magsdk/component-list.svg?style=flat-square)](https://david-dm.org/magsdk/component-list)
[![devDependencies status](https://img.shields.io/david/dev/magsdk/component-list.svg?style=flat-square)](https://david-dm.org/magsdk/component-list?type=dev)
[![Gitter](https://img.shields.io/badge/gitter-join%20chat-blue.svg?style=flat-square)](https://gitter.im/DarkPark/magsdk)


List is a component to build user interface, an instance of [Component](https://github.com/magsdk/component) module.
May be associated with [mag-data-cacher](https://github.com/magsdk/data-cacher) and [stb-component-scrollbar](https://github.com/stbsdk/component-scrollbar).


## Installation ##

```bash
npm install mag-component-list
```


## Usage ##

Add the singleton to the scope:

```js
var List = require('mag-component-list');
```

Create list instance:

```js
var list = new List({
    cycle: false,
    className: 'list',

    data: [ 
        '0',
        '1',
        '2',
        '3',
        '4'
    ],

    // custom render function
    render: function ( $item, config ) {},
    // data provider to get visible part from all data, may use mag-data-cacher 
    provider: dataProvider,
    // associated ScrollBar component link, may use stb-component-scrollbar
    scroll: new ScrollBar({}),
    size: 3,
    focusIndex: 0,
    propagate: false,
    type: List.prototype.TYPE_HORIZONTAL,
    events: {
        'focus:item': function ( event ) {
            console.log(event);
        },
        'click:item': function ( event ) {
            console.log(event);
        }
    }
});

To change data after creation:

```js
list.setData({
    focusIndex: 0,
    data: [
        'Item 0',
        'Item 1'
    ]
});
```

To change focus position by index:

```js
list.focusIndex(index);
```

To change focus item:

```js
list.focusItem($item);
```

To blur item:

```js
list.blurItem($item);
```

To mark item:

```js
list.markItem($item, true);
```


## Development mode ##

> There is a global var `DEVELOP` which activates additional consistency checks and protection logic not available in release mode.


## Contribution ##

If you have any problems or suggestions please open an [issue](https://github.com/magsdk/component-list/issues)
according to the contribution [rules](.github/contributing.md).


## License ##

`mag-component-list` is released under the [MIT License](license.md).
