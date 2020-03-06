# Template view

### Making it easier to work with templates in codeigniter 4

## Example:

#### How codeigniter 4 loads multiple views

```php
<?php namespace App\Controllers;

class Page extends \CodeIgniter\Controller
{
        public function index()
        {
                $data = [
                        'page_title' => 'Your title'
                ];

                // Here
                echo view('header');
                echo view('menu');
                echo view('content', $data);
                echo view('footer');
        }
}
```

#### How would you load it using this library

```php
class Page extends \CodeIgniter\Controller
{
        public function index()
        {
                $data = [
                        'page_title' => 'Your title'
                ];

                // Here
                $this->template->load('template_name', 'page_name', $data)
        }
}
```
## Installation

#### Add files from this package to the corresponding folder structure

```shell
CI4 # → Root Directory
└── app/
    ├── Libraries
    │   └── Template.php
```

#### Add in Base Controller

```php
/**
 * Template
 *
 * @var \App\Libraries\Template
 */
protected $template;

/**
 * Constructor.
 */
public function initController( { ...params } )
{
      // Do Not Edit This Line
      parent::initController($request, $response, $logger);

      // Loading template
      $this->template = new Template;

}
```






