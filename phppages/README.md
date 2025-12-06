### Project Structure

```
/taxtion
│
├── /assets
│   ├── /attached_assets
│   ├── /client
│   ├── /attached_assets
│   └── /styles.css
│
├── /includes
│   ├── header.php
│   └── footer.php
│
├── /pages
│   ├── index.php
│   ├── about.php
│   ├── contact.php
│   ├── countries.php
│   ├── services.php
│   ├── saudi.php
│   ├── qatar.php
│   ├── oman.php
│   ├── india.php
│   ├── hongkong.php
│   ├── bahrain.php
│   └── other country pages...
│
└── .htaccess
```

### 1. Create `header.php`

```php
<!-- includes/header.php -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title><?php echo isset($title) ? $title : 'Habibi Tax Lab'; ?></title>
    <link rel="stylesheet" href="assets/styles.css">
    <link rel="icon" href="assets/client/public/favicon.png">
</head>
<body>
    <nav id="navbar" class="navbar">
        <div class="container">
            <a href="index.php" class="logo">
                <img src="assets/attached_assets/logo/logo_tax.jpeg" alt="Habibi Tax Lab Logo">
            </a>
            <div class="nav-links">
                <a href="index.php">Home</a>
                <a href="services.php">Services</a>
                <a href="countries.php">Countries</a>
                <a href="about.php">About</a>
                <a href="contact.php">Contact</a>
            </div>
            <div class="mobile-menu-toggle" id="mobile-toggle">
                <span></span><span></span><span></span>
            </div>
        </div>
    </nav>
    <div class="mobile-menu" id="mobile-menu">
        <a href="index.php">Home</a>
        <a href="services.php">Services</a>
        <a href="countries.php">Countries</a>
        <a href="about.php">About</a>
        <a href="contact.php">Contact</a>
    </div>
```

### 2. Create `footer.php`

```php
<!-- includes/footer.php -->
    <footer class="footer">
        <div class="container">
            <div class="footer-content">
                <div class="footer-brand">
                    <h3>HABIBI TAX LAB</h3>
                    <p>Your trusted partner for global business setup, tax compliance, and financial growth. Building your legacy across borders.</p>
                </div>
                <div class="footer-links">
                    <h4>Quick Links</h4>
                    <ul>
                        <li><a href="index.php">Home</a></li>
                        <li><a href="services.php">Services</a></li>
                        <li><a href="countries.php">Countries</a></li>
                        <li><a href="about.php">About</a></li>
                        <li><a href="contact.php">Contact</a></li>
                    </ul>
                </div>
                <div class="footer-contact">
                    <h4>Contact</h4>
                    <ul>
                        <li>+971 77 604 10869</li>
                        <li>info@habibitaxlab.com</li>
                        <li>Dubai, UAE</li>
                    </ul>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2025 Habibi Tax Lab. All Rights Reserved.</p>
                <div>
                    <a href="#">Privacy Policy</a>
                    <a href="#">Terms of Service</a>
                </div>
            </div>
        </div>
    </footer>
    <script src="assets/script.js"></script>
</body>
</html>
```

### 3. Create `index.php`

```php
<!-- pages/index.php -->
<?php
$title = "Habibi Tax Lab - Global Company Setup & Compliance Experts";
include '../includes/header.php';
?>

<section id="hero" class="hero">
    <div class="hero-bg">
        <img src="assets/attached_assets/generated_images/luxury_dark_background_with_golden_world_map_abstract.png" alt="Global Business">
    </div>
    <div class="hero-content">
        <span class="badge">Global Compliance Experts</span>
        <h1>Global Company Setup <br><span>& Compliance Experts</span></h1>
        <p>Specializing in international business formation, tax registration, government compliance, banking support, and visa solutions.</p>
        <a href="contact.php" class="cta-button">Get Started Today</a>
    </div>
</section>

<!-- Add other sections like services teaser, countries teaser, etc. -->

<?php include '../includes/footer.php'; ?>
```

### 4. Create Other Pages

You can create other pages like `about.php`, `contact.php`, `countries.php`, etc., following the same structure as `index.php`. Just change the content between the header and footer as needed.

### 5. Create `.htaccess` for URL Rewriting (Optional)

If you want to remove the `.php` extension from URLs, you can create a `.htaccess` file in the root directory:

```apache
RewriteEngine On
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^([^\.]+)$ $1.php [L]
```

### 6. Update Links

Make sure to update all links in your PHP files to point to the correct `.php` files instead of `.html`.

### Conclusion

This structure allows you to maintain a clean separation of concerns, making it easier to manage your website. You can add more functionality, such as a database connection for dynamic content, as needed.