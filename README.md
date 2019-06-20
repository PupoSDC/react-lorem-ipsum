# React Lorem Ipsum

**React Lorem Ipsum** is a React library including Components and Functions to **generate placeholder text**.

When you develop a mockup page or backend API is not ready for data fetching and you have to make Frontend Development with static data until it comes, `react-lorem-ipsum` will create your gibberish texts for you.

In addition to Lorem Ipsum text, you can generate **random names, surnames, full names** and **usernames** to fill the fields about users randomly.

👍 React Lorem Ipsum is a zero-dependency, easy-to-use package.

[![NPM version][npm-image]][npm-url]
[![npm download][download-image]][download-url]
[![npm size][size-image]][size-url]

[npm-image]: https://img.shields.io/npm/v/react-lorem-ipsum.svg?style=flat-square
[npm-url]: https://npmjs.org/package/react-lorem-ipsum
[download-image]: https://img.shields.io/npm/dm/react-lorem-ipsum.svg?style=flat-square
[download-url]: https://npmjs.org/package/react-lorem-ipsum
[size-image]: https://img.shields.io/bundlephobia/min/react-lorem-ipsum.svg
[size-url]: https://npmjs.org/package/react-lorem-ipsum

**Table of Contents**

1. [Install](#install)
2. [Demo](#demo)
3. [How to Import](#how-to-import)
4. [Props](#props)
5. [Examples](#examples)
6. [License](#license)
7. [Author](#author)

## Install

[![react-lorem-ipsum](https://nodei.co/npm/react-lorem-ipsum.png)](https://npmjs.org/package/react-lorem-ipsum)

```bash
npm install react-lorem-ipsum
```

or

```bash
yarn add react-lorem-ipsum
```

## Demo

[https://fatihtelis.github.io/react-lorem-ipsum](https://fatihtelis.github.io/react-lorem-ipsum)

## How to Import

#### Component

```js
import { LoremIpsum } from 'react-lorem-ipsum';
```

#### Functions

```js
import { loremIpsum, name, surname, fullname, username } from 'react-lorem-ipsum';
```

## Props

#### LoremIpsum (Component), loremIpsum (function)

**loremIpsum** is function version of the component **LoremIpsum** which generates plain text instead of HTML. They both get the same props/inputs as a single object.

| Name                     | Type   | Default | Description                                                                               |
| ------------------------ | ------ | ------- | ----------------------------------------------------------------------------------------- |
| p                        | number | 1       | Number of paragraphs that will be generated                                               |
| avgWordsPerSentence      | number | 8       | Avarage number of words created for each sentence (standard deviation is fixed ±25%)      |
| avgSentencesPerParagraph | number | 8       | Avarage number of sentences created for each paragraph (standard deviation is fixed ±25%) |
| startWithLoremIpsum      | bool   | true    | Start with 'Lorem ipsum odor amet...' to first sentence of first paragraph                |

_Note:_ If you use loremIpsum function to generate plain text, it will return an "Array" with length of the desired count. You can use "Array.map" or similar methods to process the data. See [Examples](#examples) for details.

#### name, fullname

| Name   | Type   | Default | Description                                                                                             |
| ------ | ------ | ------- | ------------------------------------------------------------------------------------------------------- |
| gender | string | 'all'   | Gender for the generated name or full name. Possible values are **'all'**, **'male'** and **'female'**. |

#### surname, username

| Props                                                                                                                         |
| ----------------------------------------------------------------------------------------------------------------------------- |
| `surname` and `username` functions **does not take any inputs**. They just create random surnames and usernames respectively. |

## Examples

### LoremIpsum (Component)

**Code**

```js
import React from 'react';
import { render } from 'react-dom';
import { LoremIpsum } from 'react-lorem-ipsum';

render(
  <div className="text-wrapper">
    <LoremIpsum p={2} />
  </div>,
  document.getElementById('root'),
);
```

**HTML Output**

```html
<div class="text-wrapper">
  <p>
    Lorem ipsum odor amet, consectetuer adipiscing elit. Ac purus in massa egestas mollis varius;
    dignissim elementum. Mollis tincidunt mattis hendrerit dolor eros enim, nisi ligula ornare.
    Hendrerit parturient habitant pharetra rutrum gravida porttitor eros feugiat. Mollis elit
    sodales taciti duis praesent id. Consequat urna vitae morbi nunc congue.
  </p>
  <p>
    Non etiam tempor id arcu magna ante eget. Nec per posuere cubilia cras porttitor condimentum
    orci suscipit. Leo maecenas in tristique, himenaeos elementum placerat. Taciti rutrum nostra,
    eget cursus velit ultricies. Quam molestie tellus himenaeos cubilia congue vivamus ultricies.
    Interdum praesent ut penatibus fames eros ad consectetur sed.
  </p>
</div>
```

### loremIpsum (Function)

**Code 1**

```js
import React from 'react';
import { render } from 'react-dom';
import { loremIpsum } from 'react-lorem-ipsum';

render(<div className="text-wrapper">{loremIpsum()}</div>, document.getElementById('root'));
```

**HTML Output 1**

```html
<div class="text-wrapper">
  Lorem ipsum odor amet, consectetuer adipiscing elit. Imperdiet erat nullam tortor quis elit lacus
  blandit vitae. Nostra dapibus bibendum; curae magnis commodo metus vestibulum tristique. Tristique
  volutpat consectetur congue lorem pharetra habitant. Sodales gravida egestas venenatis dignissim
  molestie cursus porta. Massa lacus pulvinar aliquam mi tristique.
</div>
```

**Code 2**

```js
import React from 'react';
import { render } from 'react-dom';
import { loremIpsum } from 'react-lorem-ipsum';

render(
  <div className="text-wrapper">
    {loremIpsum({ p: 3 }).map(text => (
      <div className="text" key={text}>
        {text}
      </div>
    ))}
  </div>,
  document.getElementById('root'),
);
```

**HTML Output 2**

```html
<div class="text-wrapper">
  <div class="text">
    Lorem ipsum odor amet, consectetuer adipiscing elit. Primis eros nunc fringilla id rutrum nibh.
    Orci convallis pulvinar urna fusce at purus neque nam leo? Suspendisse semper facilisi
    parturient sit euismod placerat. Orci ante luctus praesent torquent orci commodo aptent blandit.
    Placerat arcu dui potenti; nullam taciti taciti amet.
  </div>
  <div class="text">
    Ridiculus proin etiam justo vivamus dignissim suscipit maecenas. Gravida ornare interdum ex dui
    eu faucibus dictum dis blandit. Rhoncus habitasse suscipit felis massa, ultrices auctor. Laoreet
    magnis justo velit vulputate iaculis at pulvinar augue. Condimentum suspendisse habitasse metus
    cubilia curabitur non sem. Primis nam in nulla phasellus bibendum pretium.
  </div>
  <div class="text">
    Augue malesuada massa torquent diam tortor; porttitor dis massa. Habitasse nunc ad placerat;
    ante netus gravida a porttitor. Vel aliquet hendrerit efficitur facilisis fames lacinia porta
    per. Integer euismod aenean mi hendrerit in volutpat consequat tempus turpis. Bibendum massa ad
    tincidunt, platea montes ac arcu. Penatibus elit justo adipiscing magna vulputate leo per.
  </div>
</div>
```

### name, surname, fullname, username

**Code 1**

```js
import React from 'react';
import { render } from 'react-dom';
import { name, surname, username } from 'react-lorem-ipsum';

render(
  <div className="user">
    <div className="name">{name('male')}</div>
    <div className="surname">{surname()}</div>
    <div className="username">{username()}</div>
  </div>,
  document.getElementById('root'),
);
```

**HTML Output 1**

```html
<div class="user">
  <div class="name">John</div>
  <div class="surname">Smith</div>
  <div class="username">smart_guru</div>
</div>
```

**Code 2**

```js
import React from 'react';
import { render } from 'react-dom';
import { fullname, username } from 'react-lorem-ipsum';

render(
  <div className="user">
    <div className="full-name">{fullname('female')}</div>
    <div className="username">{`@${username()}`}</div>
  </div>,
  document.getElementById('root'),
);
```

**HTML Output 2**

```html
<div class="user">
  <div class="full-name">Jennifer S. Rose</div>
  <div class="username">@smart.fox.19</div>
</div>
```

## License

`react-lorem-ipsum` is released under the MIT license.

## Author

<table>
  <tr>
    <td>
      <img src="https://github.com/fatihtelis.png?s=100" width="100">
    </td>
    <td>
      Fatih Telis<br />      
      <a href="http://fatihtelis.com" title="Fatih Telis">http://fatihtelis.com</a>
    </td>
  </tr>
</table>
