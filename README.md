# Frameworks and ORM Injection Testing

| Framework | ORM Library | Common Vulnerable Methods |
|-----------|-------------|---------------------------|
| Laravel | Eloquent ORM | whereRaw(), DB::raw() |
| Ruby on Rails | Active Record |where("name = '#{input}'") |
| Django | Django ORM | extra(), raw() |
| Spring | Hibernate | createQuery() with concatenation |
| Node.js | Sequelize | sequelize.query() |

## Techniques for Testing ORM Injection

- Manual code review: A thorough source code inspection can reveal raw query methods (such as whereRaw() in Laravel) that incorporate user inputs directly. Look for concatenated strings or unescaped inputs in ORM methods, which can indicate injection points.

- Automated scanning: Use security scanning tools that are designed to detect ORM injection vulnerabilities. These tools analyse the codebase to identify patterns that could lead to injection, such as dynamic query construction or improper input handling.
- Input validation testing: Perform manual testing by injecting payloads into application inputs to see if they affect the underlying ORM query. For example, injecting SQL control characters or keywords to determine if they alter the execution of the query.
- Error-based testing: Enter deliberately incorrect or malformed data to trigger errors. Detailed error messages can provide insights into the structure of the underlying queries and indicate potential vulnerabilities.
