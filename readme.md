# Programming Standards
--- WEBARQ Web Application Division ---

## Programming Standards

### 1. Main Languages and Frameworks
* Our main language is PHP
* Our main framework is Laravel
* Our main micro framework is Lumen

For certain projects with specific needs, sure we can use other frameworks, or even other languages.

### 2. Helpers
Helpers **MUST BE** declared as class methods or [Facades](http://laravel.com/docs/4.2/facades). For instance, `CoolApp::formatDate($date)`. Helpers in public function format, like `format_date($date)`, is **NOT ALLOWED**.

### 3. Javascripts

You **MAY NOT** put any Javascript in any spesific section files. Instead, put all Javascripts inside `/public/js/scripts.js`. This is the best practice for performance and maintainable code.

If you need to throw a variable from server, put the script in `/app/views/layout/master.blade.php`. So, `/public/js/scripts.js` will catch it.

### 4. Dynamic Content Files

All dynamic content files uploaded by the end users, such as images and PDF files, must be stored inside `/public/contents/`. Sub directories are **NOT ALLOWED**.

### 5. Revision Control

We use Git as revision control. **No other VCS is allowed**.

Make yourself fluent with it, at least the basics.

### 6. English Usage
* **MANDATORY**: file name, variable name, class name, method name, etc.
* Optional: comments, Git commit comment

## Common Standards
Beside our standards above, of course you have to be familiar with the common standards and implementing them for our works best result.

Don't get it?

Common standards means the ways, standards, rules, or best practices which are well-known in the programming community. See below for examples.

* Implement framework's conventions
* Implement framework's best practices
* No multiple line on View (MVC) files
* Put Javascript files at bottom
* Clean code, readable code, DRY, etc.
* Make Git commit comment informative

&copy; 2015 [Web Architect Technology, PT](http://www.webarq.com/)