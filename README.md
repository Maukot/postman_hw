# Postman. HW_1

### Общие шаги

1. Создание коллекции: *Collections - New - Collection*
2. Создание запроса под каждый endpoint: *Add request* (меню открывается нажатием на три точки у названия коллекции или ПКМ) либо *Duplicate* существующий реквест также через меню
3. После создания/изменения реквеста обязательно *Save*
4. Отправляем запрос кнопкой *Send*

### Создать запросы в Postman

Protocol: http  
IP: 162.55.220.72  
Port: 5005

## EP_1 /get_method
Method: GET  
request url params:   
name: str  
age: int

response:  
[  
    “Str”,  
    “Str”  
]

```
URL: http://162.55.220.72:5005/get_method

Params  
  KEY  | VALUE
  age  | 33
  name | Liubov

URL изменится на http://162.55.220.72:5005/get_method?age=33&name=Liubov

Response body
  [
      "Liubov",
      "33"
  ]
```

## EP_2 /user_info_3

Method: POST  
request form data:  
 name: str  
 age: int  
 salary: int  

response:  
{'name': name,  
          'age': age,  
          'salary': salary,  
          'family': {'children': [['Alex', 24], ['Kate', 12]],  
                     'u_salary_1_5_year': salary * 4}}

```
URL: http://162.55.220.72:5005/user_info_3

Body (form-data)    
  KEY    | VALUE
  age    | 33
  name   | Liubov
  salary | 2000
  
Response body  
  {
      "age": "33",
      "family": {
          "children": [
              [
                  "Alex",
                  24
              ],
              [
                  "Kate",
                  12
              ]
          ],
          "u_salary_1_5_year": 8000
      },
      "name": "Liubov",
      "salary": 2000
  }
```

## EP_3 /object_info_1
Method: GET  
request url params:  
 name: str  
 age: int  
 weight: int  

response:  
{'name': name,  
          'age': age,  
          'daily_food': weight * 0.012,  
          'daily_sleep': weight * 2.5}

```
URL: http://162.55.220.72:5005/object_info_1

Params  
  KEY    | VALUE
  name   | Dan
  age    | 15
  weight | 40
  
URL изменится на http://162.55.220.72:5005/object_info_1?name=Dan&age=15&weight=40

Response body  
  {
    "age": 15,
    "daily_food": 0.48,
    "daily_sleep": 100.0,
    "name": "Dan"
  }
```

## EP_4 /object_info_2
Method: GET  
request url params:  
 name: str  
 age: int  
 salary: int  

response:  
{'start_qa_salary': salary,  
          'qa_salary_after_6_months': salary * 2,  
          'qa_salary_after_12_months': salary * 2.7,  
          'qa_salary_after_1.5_year': salary * 3.3,  
          'qa_salary_after_3.5_years': salary * 3.8,  
          'person': {'u_name': [user_name, salary, age],  
                     'u_age': age,  
                     'u_salary_5_years': salary * 4.2}  
          }

```
URL: http://162.55.220.72:5005/object_info_2

Params  
  KEY    | VALUE
  name   | Dan
  age    | 15
  salary | 500
  
URL изменится на http://162.55.220.72:5005/object_info_2?name=Dan&age=15&salary=500

Response body
  {
    "person": {
        "u_age": 15,
        "u_name": [
            "Dan",
            500,
            15
        ],
        "u_salary_5_years": 2100.0
    },
    "qa_salary_after_1.5_year": 1650.0,
    "qa_salary_after_12_months": 1350.0,
    "qa_salary_after_3.5_years": 1900.0,
    "qa_salary_after_6_months": 1000,
    "start_qa_salary": 500
  }
```

## EP_5 /object_info_3
Method: GET  
request url params:  
 name: str  
 age: int  
 salary: int  

response:  
{'name': name,  
          'age': age,  
          'salary': salary,  
          'family': {'children': [['Alex', 24], ['Kate', 12]],  
                     'pets': {'cat':{'name':'Sunny',  
                                     'age': 3},  
                              'dog':{'name':'Luky',  
                                     'age': 4}},  
                     'u_salary_1_5_year': salary * 4}  
          }

```
URL: http://162.55.220.72:5005/object_info_3

Params  
  KEY    | VALUE
  name   | Ivan
  age    | 50
  salary | {{salary}}                      #взято значение переменной из окружения Environment, равное 8000
  
URL изменится на http://162.55.220.72:5005/object_info_3?name=Ivan&age=50&salary={{salary}}

Response body
  {
    "age": "50",
    "family": {
        "children": [
            [
                "Alex",
                24
            ],
            [
                "Kate",
                12
            ]
        ],
        "pets": {
            "cat": {
                "age": 3,
                "name": "Sunny"
            },
            "dog": {
                "age": 4,
                "name": "Luky"
            }
        },
        "u_salary_1_5_year": 32000
    },
    "name": "Ivan",
    "salary": 8000
}
```

## EP_6 /object_info_4

Method: GET  
request url params:  
 name: str  
 age: int  
 salary: int  

response:  
{'name': name,  
          'age': int(age),  
          'salary': [salary, str(salary * 2), str(salary * 3)]}
```
URL: http://162.55.220.72:5005/object_info_4

Params  
  KEY    | VALUE
  name   | Vera
  age    | 35
  salary | 1500
  
URL изменится на http://162.55.220.72:5005/object_info_4?name=Vera&age=35&salary=1500

Response body  
  {
    "age": 35,
    "name": "Vera",
    "salary": [
        1500,
        "3000",
        "4500"
    ]
  }
```

## EP_7 /user_info_2
Method: POST  
request form data:  
 name: str  
 age: int  
 salary: int  

response:  
{'start_qa_salary': salary,  
          'qa_salary_after_6_months': salary * 2,  
          'qa_salary_after_12_months': salary * 2.7,  
          'qa_salary_after_1.5_year': salary * 3.3,  
          'qa_salary_after_3.5_years': salary * 3.8,  
          'person': {'u_name': [user_name, salary, age],  
                     'u_age': age,  
                     'u_salary_5_years': salary * 4.2}  
          }
```
URL: http://162.55.220.72:5005/user_info_2

Body (form-data)    
  KEY    | VALUE
  age    | 35
  name   | Mary
  salary | {{salary}}
  
Response body
  {
    "person": {
        "u_age": 35,
        "u_name": [
            "Mary",
            8000,
            35
        ],
        "u_salary_5_years": 33600.0
    },
    "qa_salary_after_1.5_year": 26400.0,
    "qa_salary_after_12_months": 21600.0,
    "qa_salary_after_3.5_years": 30400.0,
    "qa_salary_after_6_months": 16000,
    "start_qa_salary": 8000
  }
```
