# Remove /public URL in  **Laravel**
--------------------------------
<h3>
<ol> 
<h3>1. Duplicate your "server.php" file.</h3>
<h3>2. rename "serve.php" to "index.php"</h3>
</ol>
</h3>

![Alt text](https://1.bp.blogspot.com/-PlzL0zkUxMM/X2gYeFXhD_I/AAAAAAAAEK0/51_llGcgEuka-dpucVwTRtawd1ERtAMNgCLcBGAsYHQ/s456/server.PNG.)
![Alt text](https://1.bp.blogspot.com/-TxuVwEFCerc/X2gYczTb5PI/AAAAAAAAEKw/Q6ARcewfRVUUQ94kr4b1g2G8pYesJaRvwCLcBGAsYHQ/s455/index.PNG.)


<h3>
<ol> 
<h3>3. Duplicate the ".htaccess" file in the public folder to the outside</h3>
</ol>
</h3>

![Alt text](https://1.bp.blogspot.com/-xYp9UPBgUBY/X2gYbqBvNJI/AAAAAAAAEKs/enp-1CUHIjoIobNtuaJHO2g1FsuXVO0GgCLcBGAsYHQ/s577/htaccess.PNG.)

<h3>
<ol> 
<h3>4. Add the code in .htaccess file</h3>
</ol>
</h3>

``` php
    <IfModule mod_rewrite.c>
        <IfModule mod_negotiation.c>
            Options -MultiViews -Indexes
        </IfModule>

    # Hide .env file
        <FilesMatch "^\.env">
            Order allow,deny
            Deny from all
        </FilesMatch>

        RewriteEngine On

    # Handle Authorization Header
        RewriteCond %{HTTP:Authorization} .
        RewriteRule .* - [E=HTTP_AUTHORIZATION:%
        {HTTP:Authorization}]

    # Redirect Trailing Slashes If Not A Folder...
        RewriteCond %{REQUEST_FILENAME} !-d
        RewriteCond %{REQUEST_URI} (.+)/$
        RewriteRule ^ %1 [L,R=301]

    # Send Requests To Front Controller...
        RewriteCond %{REQUEST_FILENAME} !-d
        RewriteCond %{REQUEST_FILENAME} !-f
        RewriteRule ^ index.php [L]

    </IfModule>
```

<br>
<br>

## Solve the problem of calling <code>{{ asset('assets/item')) }}</code> 

<h3>
<ol> 
<h3>1. go to the directory</h3>
</ol>
</h3>

```php
    laravel\framework\src\Illuminate\Fondation\helpers.php
```

<h3>
<ol> 
<h3>2. Add public/ on line 146</h3>
</ol>
</h3>

```php
 if (! function_exists('asset')) {
     /**
     * Generate an asset path for the  application.
     *
     * @param  string  $path
     * @param  bool|null  $secure
     * @return string
     */
    function asset($path, $secure = null)
    {
        return app('url')->asset("public/". $path, $secure);
    }
}
```

<br>
<br>

<h1 align="center">Official Social Media</h1>

<p align="center"><img src="https://1.bp.blogspot.com/-VgeE1MjanrE/XuFF2iuufxI/AAAAAAAAOIE/DPUU6oIUpL4purpAYrtqh0zLLmu4OFxSwCLcBGAsYHQ/s320/IMG-20200516-WA0007.jpg" width="200"></p>

<p align="center">
<a href="https://www.youtube.com/channel/UCJimeCqIntVIFFkHU5VDqxQ"><img src="https://2.bp.blogspot.com/-SISNOeaT5mw/XuFE8eoZyII/AAAAAAAAOH0/HOtgXPjJkuMQCZDapJ5OcpCTHCNGUObqwCLcBGAsYHQ/s320/youtube.png" alt="Build Status"></a>
<a href="https://www.instagram.com/cv_bud/"><img src="https://4.bp.blogspot.com/-v9440yXLL0Y/XuFFTfcp-mI/AAAAAAAAOH8/HO5AJtLJEfAd90nk5Gu_geV4VSewLH60gCLcBGAsYHQ/s320/instagram.png" alt="Total Downloads"></a>


Visit [My Profile](https://mrbudbud.github.io/) to see my profile.
