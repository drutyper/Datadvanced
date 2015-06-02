This folder structure should be suitable for starting a project that uses a database:

* Clone the repo
* `rake generate:migration <Name>` to create a migration
* `rake db:migrate` to run it
* Create models
* ... ?
* Profit

You may need to fiddle around with remotes assuming that you don't want to push to this one (which you probably don't).

## Rundown

```
.
├── Gemfile             # Details which gems are required by the project
├── README.md           # This file
├── Rakefile            # Defines `rake generate:migration` and `db:migrate`
├── config
│   └── database.yml    # Defines the database config (e.g. name of file)
├── console.rb          # `ruby console.rb` starts `pry` with models loaded
├── db
│   ├── dev.sqlite3     # Default location of the database file
│   ├── migrate         # Folder containing generated migrations
│   └── setup.rb        # `require`ing this file sets up the db connection
└── lib                 # Your ruby code (models, etc.) should go here
    └── all.rb          # Require this file to auto-require _all_ `.rb` files in `lib`
```

How many users are there? 49
User.count

What are the 5 most expensive items? Item.order(price: :desc).limit(5)

What's the cheapest electronics item? Item.order(price: :asc).limit(1)

Who lives at "489 Fritsch Island"? Do they have another address? 
Address.where(street: '489 Fritsch Island') Porter Hessel
User.find(38)
Address.where(user_id: 35)

Correct Tevin Mitchell's New York zip code to 10108.
a = Address.find(26)
a.update_attributes(zip: 10108)
a.save

How much would it cost to buy one of each piece of jewelery?
Item.where("category LIKE?", "%Jewelery%").sum(:price)
'0.22626E3',18(36)

How many total items did we sell? Order.sum(:quantity) 817

How much was spent on health? 

Simulate buying an item by inserting a User for yourself and an Order for that User (do not include this in the figures above).









