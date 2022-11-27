# WordPress hack Cleanup Code Snippets
Small snippets of code which make our life easier when trying to clean up a hacked WordPress site.

## MySQL
### Searching for shadow admin users under wp_usermeta
```
select * from wp_usermeta where (meta_value) like '%administrator%' and (user_id) not in (select id from wp_users);
```
