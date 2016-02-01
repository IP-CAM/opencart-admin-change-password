upload all to root dir of opencart
| -> If you use the source code Opencart 1.5.4.1 original overwrite all files
|
| -> If you have the Opencart 1.5.4.1 custom header, you skip overwriting the file and manually edited as follows:

-----------------------------------------------------------------------------------------------------------
*In the file admin\controller\common\header.php

Locate the following line:

$this->data['text_users'] = $this->language->get('text_users');

Insert that line:

$this->data['text_user_change_password'] = $this->language->get('text_user_change_password');


Locate the following line:

$this->data['user'] = $this->url->link('user/user', 'token=' . $this->session->data['token'], 'SSL');

Insert that line:

$this->data['change_password'] = $this->url->link('user/change_password', 'token=' . $this->session->data['token'], 'SSL');

-----------------------------------------------------------------------------------------------------------
In the file admin\language\english\common\header.php

Locate the following line:

$_['text_users']                       = 'Users';

Insert that line:

$_['text_user_change_password']        = 'User change password';

-----------------------------------------------------------------------------------------------------------
In the file admin\view\template\common\header.php

Locate the following line:

<li><a href="<?php echo $user; ?>"><?php echo $text_user; ?></a></li>

Insert before that line:

<li><a href="<?php echo $change_password; ?>"><?php echo $text_user_change_password; ?></a></li>
