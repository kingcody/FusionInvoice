# FusionInvoice

#### Self-hosted online invoicing for freelancers and small businesses

FusionInvoice is built for freelancers and small businesses who need a simple, yet powerful self-hosted web based invoicing system.


##  Requirements


  * A web host or server with:
    * PHP &gt;= 5.3.0
    * MySQL &gt;= 4.x
  * A modern and updated web browser


##  Installing FusionInvoice


For those of you comfortable with installing web applications, installing FusionInvoice should take 5 minutes or less.

  1. Download and unzip the FusionInvoice full install package.
  2. Create an empty database on your web server.
  3. Upload the FusionInvoice files to your web server, either into its own subdirectory or into the public root of the web server.
  4. Run the FusionInvoice installer from your web browser:
    * If you uploaded the files into a subdirectory, access http://www.your-domain.com/the-subdirectory/index.php/setup
    * If you uploaded the files into the root, access http://www.your-domain.com/index.php/setup

Once the installer finishes, the installation is complete and you may log into FusionInvoice using the email address and password provided during installation!


###  Removing index.php

This step is entirely optional but will make your URL's more pleasing to look at.

Instead of:


    http://your-server.com/index.php/invoice/create



You'd see:


    http://your-server.com/invoice/create



Your server or web host must have Apache mod_rewrite enabled for this to work.

####  Step 1

Edit application/config/config.php

Replace Line 29


    $config['index_page'] = 'index.php';



with


    $config['index_page'] = '';



This will change the actual links in the application to use the new URL structure.

####  Step 2

Add an .htaccess file into the root where index.php is located and place the following content in the file:


    RewriteEngine on
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteRule .* index.php/$0 [PT,L]



Once you save the file and visit your URL for FusionInvoice, you should be doing so without the index.php included.

## Documentation

[FusionInvoice 1.3 Docs](http://http://docs.fusioninvoice.com/1.3/Quick-Start-Guide.html)
