# Codecademy
Codecademy Meal Maker Project

This is my solution to Codecademy Meal Maker project.
It will generate random meals.

const menu = {
  _courses: {
    appetizers: [],
    mains: [],
    desserts: [],
  },
  get appetizers() {
    return this._course.appetizers;
  },
  set appetizers(appetizersIn) {
    this._courses.appetizers = appetizersIn;
  },
  get mains() {
    return this._courses.mains;
  },
  set mains(mainsIn) {
    this._courses.mains = mainsIn;
  },

  get desserts() {
    return this._courses.desserts;
  },
  set desserts(dessertsIn) {
    this._courses.desserts = dessertsIn;
  },
  get courses() {
    return {
      appetizers: this.appetizersIn,
      mains: this.mainsIn,
      desserts: this.dessertsIn,
    };
  },
  addDishToCourse(courseName, dishName, dishPrice) {
    const dish = {
      name: dishName,
      price: dishPrice,
    };
    this._courses[courseName].push(dish);
  },
  getRandomDishFromCourse(courseName) {
    const dishes = courseName;
    const randomIndex = Math.floor(Math.random() * dishes.length);
    return dishes[randomIndex];
  },
  generateRandomMeal() {
    const appetizer = this.getRandomDishFromCourse(this._courses.appetizers);
    const main = this.getRandomDishFromCourse(this._courses.mains);
    const desserts = this.getRandomDishFromCourse(this._courses.desserts);
    const totalPrice = appetizer.price + main.price + desserts.price;
    return `Your meal is ${appetizer.name}, ${main.name} and ${desserts.name}. \nThe price is $${totalPrice}.`;
  },
};

menu.addDishToCourse("appetizers", "Caesar Salad", 4.25);
menu.addDishToCourse("mains", "Ribeye Steak", 24.25);
menu.addDishToCourse("desserts", "Cheesecake", 4.25);
menu.addDishToCourse("appetizers", "Chicken Dumpling Soup", 5.25);
menu.addDishToCourse("mains", "Lobster", 34.25);
menu.addDishToCourse("desserts", "Ice Cream", 4.25);
menu.addDishToCourse("appetizers", "Spring Rolls", 6.25);
menu.addDishToCourse("mains", "Combination Pho", 9.95);
menu.addDishToCourse("desserts", "Che 3 Mau", 4.25);
let meal = menu.generateRandomMeal();
console.log(meal);
