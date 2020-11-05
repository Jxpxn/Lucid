# Lucid
JS Micro-Framework

## Getting Started

### Prerequisites

Use the package manager [npm](https://www.npmjs.com).

```bash
npm install
```

### Installation

Clone the repo
```sh
git clone https://github.com/tanguyprvst/Lucid.git
```
Install NPM packages
```sh
npm install
```

## Usage

### Controllers

#### Create

Create a controller in ``app/controllers``

```js
const Controller = require('../../src/controller');

class ExempleController extends Controller {

}

module.exports = ExempleController
```

#### Add routes and functions

Create your routes and methods!

```js
const Controller = require('../../src/controller');

class ExempleController extends Controller {
    getRoutes(){
        return [
            ['/', 'get', this.exempleFunc],
        ]
    }

    exempleFunc(res){
        this.render(res, {value: "Hello"});
    }
}

module.exports = ExempleController
```

### Middlewares

#### Create

Create a controller in ``app/middlewares``

```js
class ExempleMiddleware {
    
    static handle(res, request, next){
        return next(res, request);
    }
}

module.exports = ExempleMiddleware
```

#### Import

In your controller, import your middleware

```js
const ExempleMiddleware = require('../middlewares/ExempleMiddleware');
```

#### Use

And use your middleware by changing your route!

```js
['/', 'get', this.exempleFunc, ExempleMiddleware],
```


## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.
