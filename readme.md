# Programming Standards
--- WEBARQ Web Application Division ---

Version 1.0

## Programming Standards

1. [Main Languages and Frameworks](#main)
2. [PHP Coding Style](#style)
3. [Helpers](#helpers)
4. [Javascripts](#js)
5. [Database](#db)
6. [Content Files](#content-files)
7. [Revision Control](#vcs)
8. [English Usage](#english)

### <a name="main"></a>1. Main Languages and Frameworks
* Our main language is PHP
* Our main framework is Laravel (version 4.2)
* Our main micro framework is Lumen

For certain projects with specific needs, sure we can use other frameworks, or even other languages.

### <a name="style"></a>2. PHP Coding Style

You **MUST** follow Laravel's coding style.

### <a name="helpers"></a>3. Helpers
Helpers **MUST BE** declared as class methods or [Facades](http://laravel.com/docs/4.2/facades). Helpers in public function format are **NOT ALLOWED**.

Correct:

	CoolApp::formatDate($date)
	
Incorrect:

	format_date($date)

### 4. <a name="js"></a>Javascripts

You **MAY NOT** put Javascript in any spesific section file. Instead, put all Javascript inside `/public/js/scripts.js`. This is the best practice for performance and code maintainability.

If you need to throw a variable from server, put the script in `/app/views/layout/master.blade.php`. So, `/public/js/scripts.js` will catch it.

### 5. <a name="db"></a>Database
There are 4 kinds of data in our databases. They are *system data*, *default data*, *content data* and *sample data*.
#### 5.1 System Data (Development, Production)

A *system data* record is a database record which cannot be deleted as it is needed by our application system. It is created in development phase and included in [migrations](http://laravel.com/docs/4.2/migrations#creating-migrations) (not [seeds](http://laravel.com/docs/4.2/migrations#database-seeding)). Of course, its value can be changed by end users in production, yet the record itself **cannot be deleted**.

Examples:

* All rows in `settings` table.
* The `Super Administrator` or `Administrator` rows in `roles` table.

#### 5.2 Default Data (Development, Production)

A *default data* record is a database record which is needed by our application UIs or functionalities during pre-production phases. Like *system data*, it is created in development phase and included in [migrations](http://laravel.com/docs/4.2/migrations#creating-migrations) (not [seeds](http://laravel.com/docs/4.2/migrations#database-seeding)). But, it can be deleted by end users in production.

Examples:

* The default administrator (e.g. `info@webarq.com`) record in `users` table.
* The initial rows in `home_banners` table. Think about it, our Home page would be shown improperly if this table is empty.

#### 5.3 Content Data (Production)

A *content data* record is a database record created by end users on production. CRUD applies here.

Examples:

* A new record in `comments` table which is created after someone posted a comment on frontend.

#### 5.4 Sample Data (Development)

This is optional. When developing, sometimes we might need to create sample data as [seeds](http://laravel.com/docs/4.2/migrations#database-seeding) for testing purposes.

### 6. <a name="content-files"></a>Content Files

#### 6.1 Location

All content files uploaded by the end users, such as image and PDF files, must be stored inside `/public/contents/`. Sub directories are **NOT ALLOWED**.

#### 6.2 Default Content Files

This is related to the section 5.2 above.

You **MUST** save the default content files with `default-` prefix.

Example:

* `/public/contents/default-home-banner1.jpg`
* `/public/contents/default-home-banner2.jpg`
* `/public/contents/default-home-banner3.jpg`
* `/public/contents/default-form.pdf`

And those files **MUST BE** commited into Git.

### 7. <a name="vcs"></a>[Revision Control](http://en.wikipedia.org/wiki/Revision_control)

* We use Git as revision control. **No other VCS is allowed**. So, make yourself fluent with it, at least the basics.
* Avoid committing large static files, such as a PDF or mp4 file sized > 5 MB. The frontend developers might include such files when developing static company profile websites. Try not to include them in our Git.

### 8. <a name="english"></a>English Usage
You **MUST** use English for file name, variable name, class name, method name, etc.

But, you may use Indonesian language on other parts like comments on code and Git commit.

## Common Standards
Beside our standards above, of course **you have to be familiar with the common standards and implementing them** for our works best result.

Don't get it?

Common standards means the ways, standards, rules, or best practices which are well-known in the programming community. See below for examples.

* Implement framework's best practices
* No multiple line on View (of MVC) files
* Put Javascript files at bottom
* Clean code, readable code, DRY, etc.
* Make Git commit comment informative
* Implement [Semantic URL](http://en.wikipedia.org/wiki/Semantic_URL) for website (public frontend pages) URLs
* Implement [Semantic URL](http://en.wikipedia.org/wiki/Semantic_URL) for REST URLs

***
&copy; 2015 [Web Architect Technology, PT](http://www.webarq.com/)