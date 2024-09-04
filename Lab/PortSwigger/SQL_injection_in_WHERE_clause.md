# Perform a SQL injection attack that causes the application to display one or more unreleased products #

![image](https://github.com/user-attachments/assets/507090db-9519-4a53-834d-2bf00611d0a4)

When we click in `Pets` section, the web display all the items in category Pets

![image](https://github.com/user-attachments/assets/49b2dbaa-16b7-4e49-ba1c-cbd06cb18ac9)

So let's change the query above by adding `'+OR+1=1--`

![image](https://github.com/user-attachments/assets/f46474d0-6bff-4e76-a172-b4857c070fa9)


# Explaination #

- Altering Query Logic: By adding '+OR+1=1--, the SQL query might look something like this:

`SELECT * FROM products WHERE category = '' OR 1=1 --'`

- `OR 1=1` creates an always-true condition, meaning that regardless of the`category` value, the query will return all records because `1=1` is always true.
- Ignoring the Rest with `--`
