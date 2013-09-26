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

$this->insert('users', $insertData)';

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
function updateUser($id)
{

$updateData = array(
	'fieldOne' => 'fieldValue',
	'fieldTwo' => 'fieldValue'
);

$this->where('id', $id)->update('users', $updateData);

}
```

### Delete Query

```php
function deleteUser($id)
{

$this->where('id', $id)->delete('users', $updateData);

}
```
