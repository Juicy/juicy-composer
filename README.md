# &lt;juicy-composer&gt;

> Custom Element that build Shadow DOM tree according to given JSON

## Demo

[Check it live!](http://Juicy.github.io/juicy-composer)

## Install

Install the component using [Bower](http://bower.io/):

```sh
$ bower install juicy-composer --save
```

Or [download as ZIP](https://github.com/Juicy/juicy-composer/archive/master.zip).

## Usage

1. Import polyfill:

    ```html
    <script src="bower_components/webcomponentsjs/webcomponents.min.js"></script>
    ```

2. Import custom element:

    ```html
    <link rel="import" href="bower_components/juicy-composer/juicy-composer.html">
    ```

3. Start using it!

    ```html
    <juicy-composer auto-stamp setup='{
        "tagName": "my-element",
        "items": [{
            "id":"group",
            "tagName": "other-element",
            "items":[{
                "id": 0,
            }]
        }]}'></juicy-composer>
    ```
    it will build you
    ```html
    <!-- juicy-composer's shadow DOM -->
    <my-element>
        <other-element>
            <content select="_firstElementChild_"></content>
        </other-element>
        <content select="_remainingElementChildren_"></content>
    </my-element>
    ```

## Options

Attribute     | Options     | Default      | Description
---           | ---         | ---          | ---
`setup`       | *JSON*      | `{}`         | Setup to reflect shadow DOM structure. It's also a property.
`auto-stamp`  | *Boolean*   | `false`      | Set to make it stamp Shadow DOM on created and every setup change. It's also a `autoStamp` property.

## Methods

Method        | Parameters   | Returns     | Description
---           | ---          | ---         | ---
`stamp`       |              |             | Call it to imperatively stamp shadow DOM tree. If `auto-stamp` attribute is set, it's done automatically, when element is created, or setup is changed.

## Events

Event         | Description
---           | ---

## Development

In order to run it locally you'll need to fetch some dependencies and a basic server setup.

1. Install [bower](http://bower.io/) & [polyserve](https://npmjs.com/polyserve):

    ```sh
    $ npm install -g bower polyserve
    ```

2. Install local dependencies:

    ```sh
    $ bower install
    ```

3. Start development server and open `http://localhost:8080/components/juicy-composer/`.

    ```sh
    $ polyserve
    ```

## History

For detailed changelog, check [Releases](https://github.com/Juicy/juicy-composer/releases).

## License

[MIT License](http://opensource.org/licenses/MIT)
