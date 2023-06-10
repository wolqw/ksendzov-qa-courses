# Запрос №1
# http://162.55.220.72:5005/first
> 1. Отправить запрос:
# GET http://162.55.220.72:5005/first
# 2. Статус код 200:
```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
### 3. Проверить, что в body приходит правильный string.
>pm.test("Проверяем, что в body приходит правильный string", function () {
>    pm.expect(pm.response.text()).to.eql("This is the first responce from server!");
> });
### Запрос №2
> http://162.55.220.72:5005/user_info_3
> 1. Отправить запрос.
> POST http://162.55.220.72:5005/user_info_3
> form-data:
> name: YurQA
> age: 33
> salary: 10000
> 2. Статус код 200.
> pm.test("Status code is 200", function () {
>    pm.response.to.have.status(200);
});
### 3. Спарсить response body в json.
> var respJson = pm.response.json();
> 4. Проверить, что name в ответе равно name s request (name вбить руками.)
>pm.test("Person name is YurQA", function () {
>  pm.expect(respJson.name).to.eql("YurQA");
> });
### 5. Проверить, что age в ответе равно age s request (age вбить руками.)
> var age = +respJson.age
> pm.test("Person age is 33", function () {
>  pm.expect(age).to.eql(33);
> });
### 6. Проверить, что salary в ответе равно salary s request (salary вбить руками.)
> pm.test("Person salary is 10000", function () {
>  pm.expect(respJson.salary).to.eql(10000);
> });
### 7. Спарсить request.
> var reqData = request.data;
### 8. Проверить, что name в ответе равно name s request (name забрать из request.)
> pm.test('request age is equal response age', function(){
>    pm.expect(respJson.name).to.equal(reqData.name)
> });
### 9. Проверить, что age в ответе равно age s request (age забрать из request.)
> pm.test('Request age is equal response age', function(){
>    pm.expect(respJson.age).to.equal(reqData.age)
> });
### 10. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
> var RQsalary = +reqJson.salary
> pm.test('Request salary is equal response salary', function(){
>    pm.expect(respJson.salary).to.equal(RQsalary)
> });
### 11. Вывести в консоль параметр family из response.
> console.log(pm.response.json().family);
### 12. Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)
> var req_salary_1_5 = RQsalary * 4
> pm.test("u_salary_1_5_year is equal request salary multiplied by 4", function(){
>     pm.expect(respJson.family.u_salary_1_5_year).to.eql(req_salary_1_5)
>})

////////////////////////////////////////////////////////////////////////////////////////////////////////

### http://162.55.220.72:5005/object_info_3
### 1. Отправить запрос.
### GET http://162.55.220.72:5005/object_info_3?name=YurQa&age=33&salary=100000
### 2. Статус код 200
> pm.test("Status code is 200", function () {
>    pm.response.to.have.status(200);
> });
### 3. Спарсить response body в json.
> var jsonData_1 = JSON.parse(responseBody);
### 4 Спарсить request.
> var reqData_1 = pm.request.url.query.toObject();
###  5. Проверить, что name в ответе равно name s request (name забрать из request.)
> pm.test("request name is equal response name", function(){
>    pm.expect(jsonData_1.name).to.eql(reqData_1.name);
> });
### 6. Проверить, что age в ответе равно age s request (age забрать из request.)
> pm.test("request age is equal response age", function(){
>    pm.expect(jsonData_1.age).to.eql(reqData_1.age);
> });
### 7. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
> var RQsalary = + reqData_1.salary;
> pm.test("request salary is equal response salary", function(){
>    pm.expect(jsonData_1.salary).to.eql(RQsalary);
> });
### 8. Вывести в консоль параметр family из response.
> console.log(pm.response.json().family);
### 9. Проверить, что у параметра dog есть параметры name.
> pm.test("have a dog the Name parameter?", function(){
>    pm.expect(jsonData_1.family.pets.dog).to.have.property('name');
> });
### 10. Проверить, что у параметра dog есть параметры age.
> pm.test("have a dog the Age parameter?", function(){
>    pm.expect(jsonData_1.family.pets.dog).to.have.property('age');
> });
### 11. Проверить, что параметр name имеет значение Luky.
> pm.test("Does the dog name is Luky????", function(){
>    pm.expect(jsonData_1.family.pets.dog.name).to.eql('Luky')
> })
### 12. Проверить, что параметр age имеет значение 4.
> pm.test("Does age is 4?", function(){
>     pm.expect(jsonData_1.family.pets.dog.age).to.eql(4)
> })

> for (i = 0; i < RsData3.salary.length; i++){
>    console.log ("salary = ", RsData3.salary[i])
>}

### http://162.55.220.72:5005/object_info_4
### 1. Отправить запрос.
### GET http://162.55.220.72:5005/object_info_4?name=YurQA&age=33&salary=100000
> 2. Статус код 200
> pm.test("Status code is 200", function () {
>    pm.response.to.have.status(200);
> });
### 3. Спарсить response body в json.
> var RsData3 = pm.response.json();
> 4. Спарсить request.
> var RqDate3 =  pm.request.url.query.toObject();
### 5. Проверить, что name в ответе равно name s request (name забрать из request.)
> pm.test("Проверить, что name в ответе равно name s request (name забрать из request.)", function () {
>     pm.expect(RsData3.name).to.eql(RqDate3.name);
> });
### 6. Проверить, что age в ответе равно age из request (age забрать из request.)
> var RqAge = + RqDate3.age
> pm.test("Проверить, что age в ответе равно age из request (age забрать из request) ", function () {
>     pm.expect(RsData3.age).to.eql(RqAge);
> });
### 7. Вывести в консоль параметр salary из request.
> console.log('параметр salary из request = ' + RqDate3.salary);
### 8. Вывести в консоль параметр salary из response.
> console.log('параметр salary из response  = ' + RsData3.salary);
### 9. Вывести в консоль 0-й элемент параметра salary из response.
> console.log('параметр salary из response 0 = ' + RsData3.salary[0]);
### 10. Вывести в консоль 1-й элемент параметра salary параметр salary из response.
> console.log('параметр salary из response 1 = ' + RsData3.salary[1]);
### 11. Вывести в консоль 2-й элемент параметра salary параметр salary из response.
> console.log('параметр salary из response 2 = ' + RsData3.salary[2]);
### 12. Проверить, что 0-й элемент параметра salary равен salary из request (salary забрать из request.)
> pm.test("0-й элемент параметра salary равен salary из request ", function(){
>  pm.expect(RsData3.salary[0]).to.eql(+RqDate3.salary)
> });
### 13. Проверить, что 1-й элемент параметра salary равен salary*2 из request (salary забрать из request.)
> pm.test("1-й элемент параметра salary равен salary*2 из request ", function(){
>   pm.expect(+RsData3.salary[1]).to.eql(RqDate3.salary*2)
> });
### 14. Проверить, что 2-й элемент параметра salary равен salary*3 из request (salary забрать из request.)
> pm.test("2-й элемент параметра salary равен salary*2 из request ", function(){
>    pm.expect(+RsData3.salary[2]).to.eql(RqDate3.salary*3)
> });
### 15. Создать в окружении переменную name
> var env_name = RqDate3.name
### 16. Создать в окружении переменную age
> var env_age = RqDate3.age
### 17. Создать в окружении переменную salary
> var env_salary = RqDate3.salary
### 18. Передать в окружение переменную name
> pm.environment.set("name", env_name);
### 19. Передать в окружение переменную age
> pm.environment.set("age", env_age);
### 20. Передать в окружение переменную salary
> pm.environment.set("salary", env_salary);
### 21. Написать цикл который выведет в консоль по порядку элементы списка из параметра salary.
> Rsdata3.salary.forEach(salary => console.log(salary))
***
> for (i = 0; i < RsData3.salary.length; i++){
>    console.log ("salary = ", RsData3.salary[i])
> }
////////////////////////////////////////////////////////////////////////////////////////////////
### http://162.55.220.72:5005/user_info_2
### 1. Вставить параметр salary из окружения в request:
> {{salary}}
### 2. Вставить параметр age из окружения в age:
> {{age}}
### 3. Вставить параметр name из окружения в name:
> {{name}}
### 4. Отправить запрос.
> succses
### 5. Статус код 200
> pm.test("Status code is 200", function () {
>    pm.response.to.have.status(200);
> });
### 6. Спарсить response body в json.
> var jsonData5 = pm.response.json();
### 7. Спарсить request.
> var params = request.data;
### 8. Проверить, что json response имеет параметр start_qa_salary:
> pm.test("Проверить, что json response имеет параметр start_qa_salary", function () {
>    pm.expect(jsonData5).to.have.property("start_qa_salary");
> });
### 9. Проверить, что json response имеет параметр qa_salary_after_6_months:
> pm.test("Проверить, что json response имеет qa_salary_after_6_months", function () {
>    pm.expect(jsonData5).to.have.property("qa_salary_after_6_months");
> });
### 10. Проверить, что json response имеет параметр qa_salary_after_12_months:
> pm.test("Проверить, что json response имеет qa_salary_after_12_months", function () {
>    pm.expect(jsonData5).to.have.property("qa_salary_after_12_months");
> });
### 11. Проверить, что json response имеет параметр qa_salary_after_1.5_year:
> pm.test("Проверить, что json response имеет qa_salary_after_1.5_year", function () {
>    pm.expect(jsonData5).to.have.property("qa_salary_after_1.5_year");
>});
### 12. Проверить, что json response имеет параметр qa_salary_after_3.5_years:
> pm.test("Проверить, что json response имеет qa_salary_after_3.5_years", function () {
>    pm.expect(jsonData5).to.have.property("qa_salary_after_3.5_years");
> });
### 13. Проверить, что json response имеет параметр person:
> pm.test("Проверить, что json response имеет person", function () {
>    pm.expect(jsonData5).to.have.property("person");
> });
### 14. Проверить, что параметр start_qa_salary равен salary из request (salary забрать из request.):
> pm.test("Проверить, что параметр start_qa_salary равен salary из request (salary забрать из request", function () {
>    pm.expect(jsonData5.start_qa_salary).to.eql(+params.salary);
> });
### 15. Проверить, что параметр qa_salary_after_6_months равен salary*2 из request (salary забрать из request.):
> pm.test("Проверить, что параметр start_qa_salary равен salary из request (salary забрать из request", function () {
>    pm.expect(jsonData5.start_qa_salary).to.eql(+params.salary);
> });
### 16. Проверить, что параметр qa_salary_after_12_months равен salary*2.7 из request (salary забрать из request.):
> pm.test("Проверить, что параметр qa_salary_after_12_months равен salary*2.7 из request (salary забрать из request", function () {
>    pm.expect(jsonData5.qa_salary_after_12_months).to.eql(+params.salary*2.7);
> });
### 17. Проверить, что параметр qa_salary_after_1.5_year равен salary*3.3 из request (salary забрать из request.):
> pm.test("Проверить, что параметр qa_salary_after_1.5_year равен salary*3.3 из request (salary забрать из request", function () {
>     pm.expect(jsonData5['qa_salary_after_1.5_year']).to.eql(+params.salary*3.3);
> });
### 18. Проверить, что параметр qa_salary_after_3.5_years равен salary*3.8 из request (salary забрать из request.):
> pm.test("Проверить, что параметр qa_salary_after_3.5_years равен salary*3.8 из request (salary забрать из request.)", function(){
>    pm.expect(jsonData5['qa_salary_after_3.5_years']).to.equal(+params.salary*3.8)
> })
### 19. Проверить, что в параметре person, 1-й элемент из u_name равен salary из request (salary забрать из request.):
> pm.test("Проверить, что в параметре person, 1-й элемент из u_name равен salary из request (salary забрать из request.", function() {
>    pm.expect(jsonData5.person.u_name[1]).to.eql(+params.salary);
> })
### 20. Проверить, что что параметр u_age равен age из request (age забрать из request.):
> pm.test("Проверить, что что параметр u_age равен age из request (age забрать из request.):", function(){ 
>     pm.expect(jsonData5.person.u_age).to.equal(+params.age)
> })
### 21. Проверить, что параметр u_salary_5_years равен salary*4.2 из request (salary забрать из request.):
> pm.test("Проверить, что параметр u_salary_5_years равен salary*4.2 из request (salary забрать из request.)", function(){
>    pm.expect(jsonData5.person.u_salary_5_years).to.eql(+params.salary*4.2)
> });
### 22. ***Написать цикл который выведет в консоль по порядку элементы списка из параметра person.

