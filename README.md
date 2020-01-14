# Shoppingcart.php

##### Create a complete shoppingcart system with few lines of code, can be used on both small and big scale sites

The cart needs to be initalized this exact way: <code>$_SESSION['cart'] = new Cart......</code>

<br>

#### Arguments
>Arg 1 <br>
>Variable of the array containing desired variable name used later when retreiving shopping cart => form element name
>
>Arg 2 <br>
>What your $_SESSION['thisvalue'] is for your username system, if you have one. ***If not: enter false***
>
>Arg 3 <br>
>Folder to save the users shoppingcart
>
>Arg 4 <br>
>Encrypt shoppingcart file, if false: users shoppingcart file will be named as the users username

<br>

## Examples:

```html
<form method="POST">
  <p value="1034" name="articlenumber"> 1034 </p>
  <h1 value="Nuke" name="label"> Nuke </h1>
  <img value="img/uranB12_nuke.jpg" src="img/uranB12_nuke.jpg" name="image">
  <p value="Can be used as a toy or deadly weapon" type="text" name="description"> Can be used as a toy or deadly weapon </p>
  <button type="submit" name="add_to_cart"> Add To Cart </button>
</form>
```
```php
$values = array(
  "articlenmb" => "articlenumber", 
  "label" => "label",
  "img" => "image",
  "desc" => "description"
);
// DESIRED VARIABLE NAME => NAME OF INPUT IN FORM
```

<br>

*Example 1*
```php
$_SESSION['cart'] = new Cart($values, "username", "users", TRUE);
```
***$_SESSION['username']*** is the username variable, shoppingcart is saved in ***"users"*** folder as their ***encrypted username***.cart

<br>

*Example 2*
```php
$_SESSION['cart'] = new Cart($values, "user", "shoppingcarts", FALSE);
```
***$_SESSION['user']*** is the username variable, shoppingcart is saved in ***"shoppingcarts"*** folder as their ***username***.cart

<br>

## Retrieving Shopping Cart For Example
```php
foreach($_SESSION["shopping_cart"] as $keys => $values)
  {
    echo $values['label'].'<br>'; // Echo value of the articlenumber element in example form
    echo $values['desc'];
  }
```
- Outputs "Nuke" and "Can be used as a toy or deadly weapon"
