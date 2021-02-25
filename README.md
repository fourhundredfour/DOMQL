# DOMQL
A SQL-Like Query Language for the Document Object Model (DOM)

## Requirements
todo

## Installation
todo

## Usage
todo

### Simple **SELECT**
```javascript
// ...
const htmlString = "<h1>Hi <b>Daniel</b>,<br/></h1>";
const domQL = new DomQL(htmlString);
domQL.query("SELECT b FROM h1"); // Returns HTMLElement[] of selected <b> elements
```

### Simple **SELECT** with **WHERE**
```javascript
// ...
const htmlString = "<h1>Hi <b>Daniel</b>,<br/></h1>";
const domQL = new DomQL(htmlString);
domQL.query("SELECT b FROM h1 WHERE b.innerHTML = 'Daniel'"); // Returns HTMLElement[] of selected <b> elements
```

### Simple **SELECT** with a more specific selection
```javascript
// ...
const htmlString = "<h1>Hi <b>Daniel</b>,<br/></h1>";
const domQL = new DomQL(htmlString);
domQL.query("SELECT b.innerHTML FROM h1"); // Returns String[]
```

### Multiple different **SELECT**s
```javascript
// ...
const htmlString = "<h1>Hi <b>Daniel</b>,<br/></h1>";
const domQL = new DomQL(htmlString);
domQL.query("SELECT b.innerHTML, h1 FROM h1"); // Returns Object with the keys "h1" and "b.innerHTML" which contains an array of HTMLElement and String
```