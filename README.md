# Typescript-practice-solution
### question 1 : Convert the following JavaScript array into a TypeScript tuple

```js jscopy
const userInfo = [101, "Ema", "John", true,  , "2023"];
````
solution
```js jscopy
const userInfo:[number,string,string,boolean,undefined,string] = [101, "Ema", "John", true,  , "2023"];
````
### Question 2: Write a TypeScript function that takes in two arrays of numbers as parameters. The function should compare the elements in both arrays and return a new array that contains only the elements that are present in both arrays.

> For example:For example, if the first array is [1, 2, 3, 4, 5] and the second array is [2, 4, 6, 8], the function should return a new array with the elements 2 and 4 because they are present in both arrays.

> The function should handle arrays of any length and should return the resulting array in the same order as they appear in the first array.

solution

```ts jscopy
const compare = (arr1: number[], arr2: number[]) => {
	let result: number[] = [];
	for (const value of arr1) {
		if (arr2.includes(value)) {
			result.push(value);
		}
	}
	return result;
};
const array1 = [1, 2, 3, 4, 5];
const array2 = [2, 4, 6, 8];
const arrayResult = compare(array1, array2);
// console.log(arrayResult);
````

### Question 3: You have an interface for ``` Product ```, containing the  product's id, name, price, and category. You want to filter an array of Products based on a specific criterion and value.

> Write a TypeScript generic function that takes this array, a criterion , and returns a new array containing only the products that match the given criterion and value. Use a generic type parameter in the function signature to ensure type safety.

solution
```js jscopy

const productsArr:Product[]=[
	{id:1,name:'jamil',price:33,category:'new'},
	{id:2,name:'kamal',price:34,category:'brand new'},
	{id:3,name:'kabul',price:36,category:'titas'},
	{id:4,name:'mobuile',price:44,category:'jwe'},
]

const filterFn=<T extends Product,K extends keyof T>(arr:T[],criterion:K,value:T[K]):T[]=>{
return arr.filter(data=>data[criterion]===value)
}

const result33=filterFn(productsArr,'name','jamil')
console.log(result33)

```

###Question 4: Suppose you have an array of tuples, where each tuple represents a product and contains the product name, price, and quantity. Write a TypeScript function that calculates the total cost of all the products in the array, using a generic type for the tuple and a type alias for the array.

```js jscopy
type ProductTuple = [string, number, number];
type ProductsArr = Array<ProductTuple>;
const calculateTotalCoast = (arr: ProductsArr): number => {
	let result: number = 0;
	arr.map((data) => {
		const [name, price, quantity] = data;
		result += price;
	});
	return result;
};
const productsArray: ProductsArr = [
	["apple ", 99, 9],
	["fruits ", 100, 9],
];

const total = calculateTotalCoast(productsArray);
console.log(total);

```

### Question 5: Suppose you have an array of numbers in TypeScript, and you want to find the sum of all the even numbers in the array. How would you approach this problem and write code to solve it?

```js jscopy
const numArr: number[] = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
const calculateEvenNumbers = (arr: number[]): number => {
	return arr
		.filter((data) => data % 2 === 0)
		.reduce((acc, cur) => acc + cur, 0);
};
const sumOfEven = result88(arr3);
// console.log(sumOfEven);
```

### Question 6: Create an interface called Person that includes properties for name (string), age (number), and email (string). Then create an array of Person objects and write a function that takes the array and a string email as parameters, and returns the Person object that matches the email or null if no match is found.

```js jscopy
interface Person {
	name: string;
	age: number;
	email: string;
}

const PersonArr: Person[] = [
	{ name: "jodo", age: 90, email: "some@gmail.com" },
	{ name: "jodo", age: 90, email: "home@gmail.com" },
	{ name: "jodo", age: 90, email: "name@gmail.com" },
];

const SearchByEmail = <T extends Person, K>(
	arr: T[],
	email: K
): Person | null => {
	for (const value of arr) {
		if (value.email === email) {
			return value;
		}
	}
	return null;
};
const result = SearchByEmail<Person, string>(PersonArr, "name@gmail.co");
// console.log(result);
```

### Question 7: Create a TypeScript program that declares an array of numbers. Use the spread  operator to pass the elements of the array as arguments to a function that finds the minimum and maximum values of the array. Use destructuring to assign the minimum and maximum values to separate variables, and log them to the console.
```js jscopy line
const findMaxAndMin = (...arr: number[]): [number, number] => {
	const max = Math.max(...arr);
	const min = Math.min(...arr);
	return [max, min];
};

const [maxValue, minValue] = findMaxAndMin(1, 2, 3, 4, 5, 6, 7);
// console.log(maxValue, minValue);
```

### Question 8: Create a TypeScript program that declares a function that takes a string parameter with a literal type of "red", "green", or "blue", and an optional boolean parameter. If the boolean parameter is true, log the string parameter in uppercase. If the boolean parameter is false or not provided, log the string parameter in lowercase.

```js jscopy
type Params = "red" | "green" | "blue";
const caseCheck = (value: Params, condition?: boolean) => {
	if (condition) {
		return value.toUpperCase();
	} else {
		return value.toLowerCase();
	}
};
const resultd = caseCheck("blue", true);
// console.log(resultd);
```
