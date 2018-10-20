# To do WebApp 

Is a software to permit create task list about activities

Quick config
First you need to establish the variables enviroments to specific in:
```
\config\credentials.yml.enc
```
to change/add this:

```
GMAIL_USERNAME: "xxx@gmail.com"
GMAIL_PASSWORD: "yourpass"
```

Also when you decide to execute rails s before be sure to change this at db\seeds.rb:

```
User.create!(
  email:"your@gmail.com",
  name:"yourname",
  lastname:"yourlastname",
  city:"yourcity",
  country:"yourcontry",
  address:"youraddress",
  gender:"yourgender",
  about:"how about you",
  picture:"xxx",
  password: "your password"
  )


TodoList.create!(
    title:"Create new users",
    description:"Admin could create any user for the systems",
    user_id: User.first.id
  )


16.times do |k|
TodoItem.create!(
  content: "Task number: #{k}",
  todo_list_id: TodoList.first.id
  )
end

```

and when you change this structure fields then execute in shell :

```
rails db:setup
```
this will create databases, tables and data

