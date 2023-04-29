# WPUserMetaData-Edit
WordPress Edit and update user meta data

```PHP
<?php

global $current_user;
    
$user_info = get_userdata($current_user->ID);
$first_name = $user_info->first_name;

echo "<pre>";
var_dump( $user_info );
echo "</pre>";

// Will return false if the previous value is the same as $new_value.
update_user_meta( $current_user->ID, 'first_name', $_POST['first_name'] );

?>
```

```HTML
<picture>
<source srcset="<?php print get_avatar_url($current_user->ID, ['size' => '51']); ?>" media="(min-width: 992px)"/>
<img src="<?php print get_avatar_url($current_user->ID, ['size' => '40']); ?>"/>
</picture>

<form method="post">
<input type="text" name="first_name" value="<?php echo $first_name ?>">
<input type="submit" value="submit">
</form>
```
