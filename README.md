# Is the number colorful?

## Description
Write a function `isColorful` which **takes a number** as argument and **returns true if the number is colorful**, false otherwise.

A colorful number is a number where all the products of consecutive subsets of digit are different. Confused? Here are two examples:
- 263 is a colorful number because (2, 6, 3, 2x6, 6x3, 2x6x3) are all different
- 236 is not because (2, 3, 6, 2x3, 3x6, 2x3x6) has 6 twice

Examples:
```javascript
isColorful(263)
//returns true

isColorful(236)
//returns false
```

## Requirements
- Pass all the tests
- To run the tests: `mocha myFile.test.js`


-----------------------------------------


const isColorful = (num) => {
    // your code here
}

module.exports = isColorful;


-----------------------------------------


const assert = require('assert');
const isColorful = require('./isColorful');

describe('isColorful', () => {
    it('Should load a function', () => {
        assert.strictEqual(typeof isColorful, 'function');
    });
    it('Should return true', () => {
        assert.strictEqual(isColorful(263), true);
    });
    it('Should return false', () => {
        assert.strictEqual(isColorful(236), false);
    });
    it('Should return false', () => {
        assert.strictEqual(isColorful(132), false);
    });
    it('Should return true', () => {
        assert.strictEqual(isColorful(4327), true);
    });
})



-----------------------------------------


# Solution:


const isColorful = (num) => {

    const digits = ("" + num).split("");
    for (let i = 0; i < digits.length; i++) {
        if (digits[i] * digits[i + 1] == digits[i + 2]) {
            return false;
        } else if (digits[i] * digits[i + 1] == digits[i + 1]) {
            return false;
        } else {
            return true;
        }
    }
};

module.exports = isColorful;

