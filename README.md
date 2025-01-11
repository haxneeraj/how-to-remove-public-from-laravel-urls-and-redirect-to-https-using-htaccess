# Laravel .htaccess: Remove Public from URL and Redirect to HTTPS  

## 🚀 Overview  
This repository provides a simple and effective solution to **remove the "public" from Laravel URLs** and **force HTTPS redirection** using the `.htaccess` file.  

### Why Optimize Laravel URLs?  
- Enhance **SEO rankings** by improving URL structure.  
- Improve user experience with cleaner and more professional URLs.  
- Secure your application with mandatory HTTPS redirection.  

---

## 📝 Features  
- 📂 **Remove "public" from Laravel URLs** without modifying core files.  
- 🔒 **Redirect HTTP traffic to HTTPS** for enhanced security.  
- 💡 Easy-to-follow instructions with ready-to-use `.htaccess` file.  

---

## 📜 Step-by-Step Guide  

### 1. Update the `.htaccess` File  
Replace the contents of your Laravel project's root `.htaccess` file with the following code:  

```apache
<IfModule mod_rewrite.c>
    RewriteEngine On

    # Redirect to HTTPS
    RewriteCond %{HTTPS} !=on
    RewriteRule ^ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]

    # Remove "public" from URL
    RewriteCond %{REQUEST_URI} !^/public/
    RewriteRule ^(.*)$ /public/$1 [L]
</IfModule>
