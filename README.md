# SmallestTemplateEngine for PHP (just ~132 Characters)

## CLASS

```sh
class T{public $p;function v($f,$d=[]){foreach($d as $k=>$v){$$k=$v;}ob_start();require($this->p.$f.'.php');return ob_get_clean();}}
```

## USAGE

```sh
// take an instance
$theme = new T();

// set template path
$theme-p = __ DIR __."/resources/";


// assign variables in array and access them in view file
 $data = [
	'title'=>'Your Site Title',
	'var1'=>'value1'
];

// no need to add .php at the end of file
// call header and pass optional $data variable in second option
echo $theme->v('templates/header',$data);

// call home file and pass optional $data variable in second option
echo $theme->v('views/pages/home',$data);

// call footer and pass optional $data variable in second option
echo $theme->v('templates/footer',$data);
```

## in Template Views

```sh
<!DOCTYPE HTML>
<html>
  <head>
	  <title><?php echo $title; ?></title>
  </head>
  <body>
	  <?php echo $var1; ?>
  </body>
</html>
```