# HW.-Postman-2


## http://162.55.220.72:5005/first
1. Отправить запрос.
2. Статус код 200
3. Проверить, что в body приходит правильный string.
```
let req_f = request.data
let resp_f = pm.response;
pm.test("First test", function () {
    pm.response.to.have.body("This is the first responce from server!ss");
});
```

## http://162.55.220.72:5005/user_info_3
1. Отправить запрос.
2. Статус код 200
3. Спарсить response body в json.
```
let resp_f = pm.response.json();
let resp_name = resp_f.name
let resp_age = +resp_f.age
let resp_salary = +resp_f.salary
let resp_salary1_5=+resp_f.family.u_salary_1_5_year
```
4. Проверить, что name в ответе равно name s request *(name вбить руками.)*
```
pm.test("check_name", function () {
    pm.expect(resp_name).to.eql("Inna1");
});
```
4.Проверить, что age в ответе равно age s request *(age вбить руками.)*
```
pm.test("check_age", function () {
    pm.expect(resp_age).to.eql(35);
});
```
5.Проверить, что salary в ответе равно salary s request *(salary вбить руками.)*
```
pm.test("check_salary", function () {
    pm.expect(resp_salary).to.eql(200);
});
```
6.Спарсить request.
```
let req_f = request.data
let req_name = req_f.name
let req_age = +req_f.age
let req_salary= +req_f.salary
```
7. Проверить, что name в ответе равно name s request *(name забрать из request.)*
```
pm.test("check_name1", function () {
    pm.expect(resp_name).to.eql(req_name);
});
```
8.Проверить, что age в ответе равно age s request *(age забрать из request.)*
```
pm.test("check_age1", function () {
    pm.expect(req_age).to.eql(resp_age);
});
```
9.Проверить, что salary в ответе равно salary s request *(salary забрать из request.)*
```
pm.test("check_salary1", function () {
    pm.expect(req_salary).to.eql(resp_salary);
});
```
10.Вывести в консоль параметр family из response.
```
console.log(resp_f.family)
```
11.Проверить что u_salary_1_5_year в ответе равно salary*4 *(salary забрать из request)*
```
pm.test("check_salary2", function () {
    pm.expect(req_salary*4).to.eql(resp_salary1_5);
});
```

## http://162.55.220.72:5005/object_info_3
1. Отправить запрос.
2. Статус код 200
3. Спарсить response body в json.
```
let resp_f = pm.response.json()
let resp_name = resp_f.name
let resp_age= resp_f.age
let resp_salary = +resp_f.salary
```
3.Спарсить request.
```
let req_f= request.data
  let req_name= req_f.name
    let req_age = req_f.age
  let req_salary= +req_f.salary
```
4.Проверить, что name в ответе равно name s request *(name забрать из request.)*
```
pm.test("Check_name", function () {
    pm.expect(resp_name).to.eql(req_name);
});
```
5.Проверить, что age в ответе равно age s request *(age забрать из request.)*
```
pm.test("Check_age", function () {
    pm.expect(resp_age).to.eql(req_age);
});
```
6.Проверить, что salary в ответе равно salary s request (salary забрать из request.)
```
pm.test("Check_salary", function () {
    pm.expect(resp_salary).to.eql(req_salary);
});
```
7.Вывести в консоль параметр family из response.
```
console.log(resp_f.family)
```
8.Проверить, что у параметра dog есть параметры **name**.
```
let resp_dog_name = resp_f.family.pets.dog
pm.test("Check_dog_name", function () {
    pm.expect (resp_dog_name).to.have.property("name");
});
```
9.Проверить, что у параметра dog есть параметры **age**.
```
pm.test("Check_dog_age", function () {
    pm.expect (resp_dog_name).to.have.property("age");
});
```
10.Проверить, что параметр **name** имеет значение **Luky**.
```
let resp_dog_name_is = resp_f.family.pets.dog.name
pm.test("Check_dog_name_is", function () {
    pm.expect (resp_dog_name_is).to.eql("Luky");
});
```
11.Проверить, что параметр **age** имеет значение **4**.
```
let resp_dog_age_is= +resp_f.family.pets.dog.age
pm.test("Check_dog_age_is", function () {
    pm.expect (resp_dog_age_is).to.eql(4);
});
```   
  
## http://162.55.220.72:5005/object_info_4
1. Отправить запрос.
2. Статус код 200
3. Спарсить response body в json.
```
let resp_age = resp_f.age
 let req_age= +req_u.age
let req_salary=+req_u.salary
let resp_salary = resp_f.salary
```
3.Спарсить request.
```
let req_u = pm.request.url.query.toObject() 
 let req_name = req_u.name 
let resp_f = pm.response.json()
  let resp_name = resp_f.name
```

4. Проверить, что name в ответе равно name s request (name забрать из request.)
```
pm.test("Check_name", function () {
    pm.expect(resp_name).to.eql(req_name);
});
```
7.Проверить, что age в ответе равно age из request (age забрать из request.)
```
pm.test("Check_age", function () {
    pm.expect(resp_age).to.eql(req_age);
});
```
8.Вывести в консоль параметр salary из request.
```
console.log ("salary_all:"+req_salary)
```
9.Вывести в консоль параметр salary из response.
```
console.log ("salary_all:"+resp_salary)
```
10.Вывести в консоль 0-й элемент параметра salary из response.
```
console.log ("salary1:" +resp_salary[0])
```
11.Вывести в консоль 1-й элемент параметра salary параметр salary из response.
```
console.log ("salary2:" +resp_salary[1])
```
12.Вывести в консоль 2-й элемент параметра salary параметр salary из response.
```
console.log ("salary3:" +resp_salary[2])
```
13.Проверить, что 0-й элемент параметра salary равен salary из request (salary забрать из request.)
```
pm.test("Check_salary1", function () {
    pm.expect(resp_salary[0]).to.eql(req_salary);
});
```
14.Проверить, что 1-й элемент параметра salary равен salary*2 из request (salary забрать из request.)
```
pm.test("Check_salary2", function () {
    pm.expect(+resp_salary[1]).to.eql(req_salary*2);
});
```
15.Проверить, что 2-й элемент параметра salary равен salary*3 из request (salary забрать из request.)
```
pm.test("Check_salary3", function () {
    pm.expect(+resp_salary[2]).to.eql(req_salary*3);
});
```
16.Создать в окружении переменную name
```
Environments --> Variable --> name
```
17.Создать в окружении переменную age
```
Environments --> Variable --> age
```
18.Создать в окружении переменную salary
```
Environments --> Variable --> salary
```
19. Передать в окружение переменную name
```
pm.environment.set("name", resp_name);
```

20.Передать в окружение переменную age
```
pm.environment.set("age", resp_age);
```
21.Передать в окружение переменную salary
```
pm.environment.set("salary", resp_salary);
```
21. Написать цикл который выведет в консоль по порядку элементы списка из параметра salary.
```
resp_salary.forEach(element => console.log(element))
```

## http://162.55.220.72:5005/user_info_2
1.Вставить параметр salary из окружения в request
```
На вкладке form-data в value  поставить {{  и выбрать в всплывающей подсказке “salary” , закрыть }}
```
2.Вставить параметр age из окружения в age
```
На вкладке form-data в value  поставить {{  и выбрать в всплывающей подсказке “age” , закрыть }}
```
3.Вставить параметр name из окружения в name
```
На вкладке form-data в value  поставить {{  и выбрать в всплывающей подсказке “name” , закрыть }}
```
4. Отправить запрос.
5. Статус код 200
6. Спарсить response body в json.
```
let req_f = request.data
```
7.Спарсить request.
```
let resp_f= pm.response.json();
```
8.Проверить, что json response имеет параметр start_qa_salary
```
pm.test("8.Check_params1", function () {
    pm.expect(resp_f).to.have.property('start_qa_salary');
});
```
9.Проверить, что json response имеет параметр qa_salary_after_6_months
```
pm.test("9.Check_params2", function () {
    pm.expect(resp_f).to.have.property('qa_salary_after_6_months');
});
```
10.Проверить, что json response имеет параметр qa_salary_after_12_months
```
pm.test("10.Check_params3", function () {
    pm.expect(resp_f).to.have.property('qa_salary_after_12_months');
});
```
11.Проверить, что json response имеет параметр qa_salary_after_1.5_year
```
pm.test("11.Check_params4", function () {
    pm.expect(resp_f).to.have.property('qa_salary_after_1.5_year');
});
```
12.Проверить, что json response имеет параметр qa_salary_after_3.5_years
```
pm.test("12.Check_params5", function () {
    pm.expect(resp_f).to.have.property('qa_salary_after_3.5_years');
});
```
13.Проверить, что json response имеет параметр person
```
pm.test("13.Check_params6", function () {
    pm.expect(resp_f).to.have.property('person');
});
```
14.Проверить, что параметр start_qa_salary равен salary из request (salary забрать из request.)
```
let req_salary= +req_f.salary
let resp_salary=+resp_f.start_qa_salary

pm.test("14.Check_salary", function () {
    pm.expect(resp_salary).to.eql(req_salary);
});
```
15.Проверить, что параметр qa_salary_after_6_months равен salary*2 из request (salary забрать из request.)
```
let resp_salary_after_6months = +resp_f.qa_salary_after_6_months
pm.test("15.Check_qa_salary_after_6_months", function () {
    pm.expect(resp_salary_after_6months).to.eql(req_salary*2);
});
```
16.Проверить, что параметр qa_salary_after_12_months равен salary*2.7 из request (salary забрать из request.)

```let resp_salary_after_12months = +resp_f.qa_salary_after_12_months
pm.test("16.Check_qa_salary_after_12_months", function () {
    pm.expect(resp_salary_after_12months).to.eql(req_salary*2.7);
});
```
17.Проверить, что параметр qa_salary_after_1.5_year равен salary*3.3 из request (salary забрать из request.)
```
  let resp_salary_after_1_5_year = +resp_f["qa_salary_after_1.5_year"]
pm.test("17.Check_qa_salary_after_1_5_year", function () {
    pm.expect(resp_salary_after_1_5_year).to.eql(req_salary*3.3);
});
```
18.Проверить, что параметр qa_salary_after_3.5_years равен salary*3.8 из request (salary забрать из request.)
```
let resp_salary_after_3_5_year = +resp_f["qa_salary_after_3.5_years"]
pm.test("18.Check_qa_salary_after_3_5_year", function () {
    pm.expect(resp_salary_after_3_5_year).to.eql(req_salary*3.8);
});
```
19.Проверить, что в параметре person, 1-й элемент из u_name равен salary из request (salary забрать из request.)
```
pm.test("19.Check_params7", function () {
    pm.expect(resp_f.person.u_name[1]).to.eql(req_salary);
});
```
20.Проверить, что что параметр u_age равен age из request (age забрать из request.)
```
pm.test("20.Check_params8", function () {
    pm.expect(resp_f.person.u_age).to.eql(+req_f.age);
});
```
21.Проверить, что параметр u_salary_5_years равен salary*4.2 из request (salary забрать из request.)
```
pm.test("21.Check_params8", function () {
    pm.expect(resp_f.person.u_salary_5_years).to.eql(+req_f.salary*4.2);
});
```
