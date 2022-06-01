# REDMAP
**Sitemap.xml for CMS 1C Bitrix** by [Ivan Shabanov](https://github.com/IvanShabanov)

1) Copy files to php_interface/include/

2) Set up the sitemap.php file   
- [ ] Set up all infoblocks so that they correctly form links to pages. 
- [ ] Enable All infoblocks that need to be output to a file
```php
      $arBlocks[] = array(
            'IBLOCK_ID' => 1, 
            'SECTION' => 'Y', 
            'DETAIL' => 'Y'   
        );
 ```           
- [ ] Add all menu files used on the site
   
     ```php
     $sitemap->AddPagesFromMenuFile('.top.menu.php', $http.$host); 
     ```  
- [ ]  Add Pages
    ```php
    $sitemap->AddPage($http.$host.'/stock/');
    ```
- [ ] Add ignored pages (pages that should not be included in the file)
     ```php
      $sitemap->AddIgnorePage($http.$host.'/hidden/');
      
3) in init.php add a line
      ```php
      include_once('sitemap.php');
      ```
4) Add agent to 
      GenerateSitemapXmlExt();

[Download releases](https://github.com/ilyayak/REDMAP/releases/)

