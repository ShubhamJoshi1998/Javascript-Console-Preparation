# 🟢 Day 2 — `this` Keyword

Today we'll focus entirely on JavaScript `this`.

Difficulty: Basic → Intermediate → Interview Traps 🔥

Rule: Don't execute the code. Predict the exact console output/error.

---

## Q1

    console.log(this);

---

## Q2

    function test() {
        console.log(this);
    }

    test();

---

## Q3

    const obj = {
        name: "Shubham",
        test: function () {
            console.log(this.name);
        }
    };

    obj.test();

---

## Q4

    const obj = {
        name: "Shubham",
        test() {
            console.log(this);
        }
    };

    obj.test();

---

## Q5

    const obj = {
        name: "Shubham",
        test: function () {
            function inner() {
                console.log(this.name);
            }

            inner();
        }
    };

    obj.test();

---

## Q6

    const obj = {
        name: "Shubham",
        test: function () {
            const inner = () => {
                console.log(this.name);
            };

            inner();
        }
    };

    obj.test();

---

## Q7

    const obj = {
        name: "Shubham",
        test: () => {
            console.log(this.name);
        }
    };

    obj.test();

---

## Q8

    const obj = {
        name: "Shubham",
        test: function () {
            console.log(this.name);
        }
    };

    const fn = obj.test;

    fn();

---

## Q9

    const obj1 = {
        name: "A",
        test: function () {
            console.log(this.name);
        }
    };

    const obj2 = {
        name: "B"
    };

    obj2.test = obj1.test;

    obj2.test();

---

## Q10

    const obj = {
        name: "Shubham",
        test() {
            const fn = this.test;
            fn();
        }
    };

    obj.test();

---

## Q11

    const obj = {
        name: "Shubham",

        test() {
            setTimeout(function () {
                console.log(this.name);
            }, 0);
        }
    };

    obj.test();

---

## Q12

    const obj = {
        name: "Shubham",

        test() {
            setTimeout(() => {
                console.log(this.name);
            }, 0);
        }
    };

    obj.test();

---

## Q13

    const obj = {
        name: "Shubham",

        test: () => {
            setTimeout(() => {
                console.log(this.name);
            }, 0);
        }
    };

    obj.test();

---

## Q14

    const person = {
        name: "Alice",

        greet() {
            console.log(this.name);
        }
    };

    const anotherPerson = {
        name: "Bob"
    };

    person.greet.call(anotherPerson);

---

## Q15

    const person = {
        name: "Alice",

        greet() {
            console.log(this.name);
        }
    };

    const anotherPerson = {
        name: "Bob"
    };

    person.greet.apply(anotherPerson);

---

## Q16

    const person = {
        name: "Alice",

        greet() {
            console.log(this.name);
        }
    };

    const anotherPerson = {
        name: "Bob"
    };

    const fn = person.greet.bind(anotherPerson);

    fn();

---

## Q17

    const obj = {
        name: "A",

        test() {
            console.log(this.name);
        }
    };

    const fn = obj.test.bind({
        name: "B"
    });

    fn.call({
        name: "C"
    });

---

## Q18

    const obj = {
        name: "A",

        test() {
            console.log(this.name);
        }
    };

    const fn = obj.test;

    fn.call({
        name: "B"
    });

---

## Q19

    const obj = {
        name: "A",

        test: () => {
            console.log(this.name);
        }
    };

    obj.test.call({
        name: "B"
    });

---

## Q20

    const obj = {
        name: "A",

        test() {
            const arrow = () => {
                console.log(this.name);
            };

            arrow.call({
                name: "B"
            });
        }
    };

    obj.test();

---

## Q21

    const obj = {
        name: "A",

        test() {
            return function () {
                console.log(this.name);
            };
        }
    };

    obj.test()();

---

## Q22

    const obj = {
        name: "A",

        test() {
            return () => {
                console.log(this.name);
            };
        }
    };

    obj.test()();

---

## Q23

    const obj1 = {
        name: "A",
        test() {
            console.log(this.name);
        }
    };

    const obj2 = {
        name: "B",
        test: obj1.test
    };

    const obj3 = {
        name: "C",
        test: obj2.test
    };

    obj3.test();

---

## Q24

    const obj = {
        name: "A",

        test() {
            console.log(this.name);

            const fn = () => {
                console.log(this.name);
            };

            fn();
        }
    };

    const fn = obj.test;

    fn();

---

## Q25

    const obj = {
        name: "A",

        test() {
            console.log(this.name);

            const arrow = () => {
                console.log(this.name);
            };

            return arrow;
        }
    };

    const fn = obj.test.call({
        name: "B"
    });

    fn.call({
        name: "C"
    });
