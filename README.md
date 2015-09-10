Normal Mode


How many users are there? User.count
What are the 5 most expensive items? Item.select('title').order(price: :desc).limit(5)
What’s the cheapest book? Item.select('title', 'price').where(category: :Books).order(price: :asc).limit(1)
Who lives at “6439 Zetta Hills, Willmouth, WY”? Do they have another address?User.find(40)
Address.where(user_id: 40)

Correct Virginie Mitchell’s address to “New York, NY, 10108”.User.select('id').where(first_name: 'Virginie')
Address.update(39, :city => 'New York', :state => 'NY', :zip => "10108")

How much would it cost to buy one of each tool? Item.select('price').where(category: "Tools").sum('price')

How many total items did we sell? Order.sum('quantity')2125

How much was spent on books?
SELECT SUM(price * quantity) FROM orders INNER JOIN items ON orders.item_id = items.id WHERE LOWER(category) LIKE '%book%';

Simulate buying an item by inserting a User for yourself and an Order for that User.


