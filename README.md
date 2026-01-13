# Frameworks and ORM Injection Testing

| Framework | ORM Library | Common Vulnerable Methods |
|-----------|-------------|---------------------------|
| Laravel | Eloquent ORM | whereRaw(), DB::raw() |
| Ruby on Rails | Active Record |where("name = '#{input}'") |
| Django | Django ORM | extra(), raw() |
| Spring | Hibernate | createQuery() with concatenation |
| Node.js | Sequelize | sequelize.query() |
