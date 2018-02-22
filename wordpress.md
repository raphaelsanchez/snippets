# Code Snippets pour Wordpress

## Migration : Changer le nom de domaine

```
# Changer l'URL du site
UPDATE wp_options
SET option_value = replace(option_value, 'http://www.ancien-site.com', 'http://www.nouveau-site.com')
WHERE option_name = 'home'
OR option_name = 'siteurl';

# Changer l'URL des GUID
UPDATE wp_posts
SET guid = REPLACE (guid, 'http://www.ancien-site.fr', 'http://www.nouveau-site.fr');

# Changer l'URL des médias dans les articles et pages
UPDATE wp_posts
SET post_content = REPLACE (post_content, 'http://www.ancien-site.fr', 'http://www.nouveau-site.fr');

# Changer l'URL des données meta
UPDATE wp_postmeta
SET meta_value = REPLACE (meta_value, 'http://www.ancien-site.com','http://www.nouveau-site.com');
```
