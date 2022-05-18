```js
const users = [
  { name: "Fortran", age: "2000-05-18" },
  { name: "Pascal", age: "2000-06-20" },
  { name: "Kossigan", age: "1888-02-02" },
  { name: "Toto", age: "1996-07-20" },
  { name: "Eugène", age: "1904-10-24" },
  { name: "Modeste", age: "1894-08-31" },
  { name: "Adeshina", age: "1992-02-22" },
  { name: "Steeve", age: "1994-02-20" },
];

const vowels = ["a", "e", "i", "u", "o"];

/* write a fuction to display user with names than start with vowels */
const startWithVowel = users.filter(function (user) {
  return vowels.includes(user.name[0].toLocaleLowerCase());
});
console.log(startWithVowel);

/* write a fuction to display user with names than start with consonants */
const startWithConsonants = users.filter(function (user) {
  return !vowels.includes(user.name[0].toLocaleLowerCase());
});
console.log(startWithConsonants);

/* console.log(
  users.map(function (user) {
    const tempUser = { ...user };
    tempUser.name = tempUser.name.toUpperCase();
    return tempUser;
  })
); */

/* write a fuction to display the users name only */
const names = users.map(function (user) {
  return user.name;
});
console.log(names.join(`\n`), users);

/* write a fuction to display user with age greater than 18 years old */
const adults = users.filter(function (user) {
  const now = new Date();

  user.age; // YYYY-MM-DD
  const tab = user.age.split("-");
  /* const bY = +tab[0];
  const bM = +tab[1] - 1;
  const bD = +tab[2]; */
  const [bY, bM, bD] = tab;

  const birthDate = new Date(bY, bM, bD);

  const ageInSecond = now - birthDate;
  const yearInMilliSeconds = 60 * 60 * 24 * 365 * 1000;
  const age = Math.floor(ageInSecond / yearInMilliSeconds);

  return age > 18;
});
console.log(adults);
```
