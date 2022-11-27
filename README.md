# WordPress Hack Cleanup Code Snippets
Small snippets of code which make our life easier when trying to clean up a hacked WordPress site.

## MySQL
### Searching for shadowed admin users under wp_usermeta
Sometimes a backdoor allows the  hacker to inject WP admin users which aren't visible through the WordPress Dashboard User Page. Even though you can see that the total count of admins is more than the admin listed  in the page you cannot search or view those admin users. The MySQL query below shows all accounts under the admin user role which exist in the wp_usermeta table but their user_id cannot be found within the wp_users table.

```
select * from wp_usermeta where (meta_value) like '%administrator%' and (user_id) not in (select id from wp_users);
```

# [Contributing](CONTRIBUTING.md)

Pull requests and issues with suggestions are welcome! Please read the [CONTRIBUTING](CONTRIBUTING.md) guidelines before submitting a PR.
