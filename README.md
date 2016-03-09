# composer role
  ansible-galaxy install -p ./roles geerlingguy.composer
  
# ansible + Drupal PAreviewsh

pareviewsh.yml
 - change `hosts: localhost`
 - change `user_home_path: /home/michaelh`
               `user_name: michaelh`
 - ` sudo ansible-playbook pareviewsh.yml  -k`
 
    vim .bash_aliases
    source .bash_aliases
 
 `alias drupalcs="phpcs --standard=Drupal --extensions='php,module,inc,install,test,profile,theme,js,css,info,txt'"`
 `alias drupalcbf="phpcbf --standard=Drupal --extensions='php,module,inc,install,test,profile,theme,js,css,info,txt'"`
  

