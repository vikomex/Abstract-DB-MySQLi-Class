Abstract-DB-MySQLi-Class
========================
To utilize this class, first import class.db.php and constants.db.php into your project, and require it.

```php
require_once('class.db.php');
require_once('constants.db.php');
```

After that, extend abstract DB class to your model

### Extend Class

```php
class Foo extends DB
{
	function bar()
	{

	}
}
```

Now, prepare your data, and call the necessary methods. 

### Insert Query

```php
function insertUser()
{

	$insertData = array(
	'login' => 'vikomex',
	'password' => 'password'
	);

$this->insert('users', $insertData);

}
```

### Select Query

```php
function selectAllUsers()
{

$results = $this->get('users', 'numberOfRows-optional');

return $results;

}
```

### Update Query

```php
$updateData = array(
	'fieldOne' => 'fieldValue',
	'fieldTwo' => 'fieldValue'
);

$this->where('id', int)->update('users', $updateData);

```

### Delete Query

```php
$this->where('id', int)->delete('users', $updateData);
```

### Generic Query Method

```php

$results = $this->query('SELECT * from posts');

print_r($results); 
```

### Raw Query Method

```php
$params = array(3, 'My Title');
$results = $this->rawQuery("SELECT id, title, body FROM posts WHERE id = ? AND tile = ?", $params);
print_r($results);

// will handle any SQL query

$params = array(10, 1, 10, 11, 2, 10);
$results = $this->rawQuery("(SELECT a FROM t1 WHERE a = ? AND B = ? ORDER BY a LIMIT ?) UNION(SELECT a FROM t2 WHERE a = ? AND B = ? ORDER BY a LIMIT ?)", $params);
print_r($results);
```


### Where Method
This method allows you to specify the parameters of the query.

```php
$results = $this->where('id', int)->where('title', string)->get('tableName');
print_r($results); 
```

