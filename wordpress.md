# Code Snippets pour Wordpress

## Migration : Changer le nom de domaine

```
# Changer l'URL du site
UPDATE PREFIX_options
SET option_value = replace(option_value, 'http://www.ancien-site.com', 'http://www.nouveau-site.com')
WHERE option_name = 'home'
OR option_name = 'siteurl';

# Changer l'URL des GUID
UPDATE PREFIX_posts
SET guid = REPLACE (guid, 'http://www.ancien-site.com', 'http://www.nouveau-site.com');

# Changer l'URL des médias dans les articles et pages
UPDATE PREFIX_posts
SET post_content = REPLACE (post_content, 'http://www.ancien-site.com', 'http://www.nouveau-site.com');

# Changer l'URL des données meta
UPDATE PREFIX_postmeta
SET meta_value = REPLACE (meta_value, 'http://www.ancien-site.com','http://www.nouveau-site.com');
```
