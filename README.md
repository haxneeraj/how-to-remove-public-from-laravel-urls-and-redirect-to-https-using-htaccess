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

### 1. Create the `.htaccess` File in your main project directory 
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
```

## 2. Test Your URLs
Access your Laravel app using a clean URL, e.g., `https://example.com`.  
Verify that both **HTTP-to-HTTPS redirection** and "public" removal work flawlessly.

---

## 🌟 Benefits
- **SEO-Friendly URLs**: Boost your website's visibility on search engines.  
- **Enhanced Security**: Redirect all traffic to HTTPS, ensuring secure connections.  
- **Professional Look**: Eliminate unnecessary "public" in URLs for a cleaner appearance.  

---

## 📊 Performance Tracking
To measure the impact of these optimizations:  
1. Use tools like **Google Search Console** to monitor your site’s performance.  
2. Check your page rankings for keywords like:  
   - `Laravel remove public from URL`  
   - `Laravel HTTPS redirect`  

---

## 📚 Additional Resources
- [Laravel Documentation](https://laravel.com/docs)  
- [Mod_Rewrite Apache Module](https://httpd.apache.org/docs/current/mod/mod_rewrite.html)  


---

## 📧 Contact
Created by **Neeraj Saini**  
- **[LinkedIn](https://www.linkedin.com/in/hax-neeraj)**  

---

## ⭐ Show Your Support
If you find this repository helpful, give it a star ⭐ and share it with the community!

---


