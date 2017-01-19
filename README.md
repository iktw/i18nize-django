# django_i18nize
Django i18nize extends the i18nize python client. This package contains template tag for rendering translation and management command for fetching translations.


```pip install django_i18nize```


## Example configuration (settings.py)
```python
DJANGO_I18NIZE_CONFIG = {
    "project_id": "852c3729-6098-410e-ad9e-9783958bbc2d",
    "live": False,
    'destination_dir': os.path.realpath(os.path.join(REPO_DIR, 'staticfiles', 'locale'))
}
```

### 1. Template tag with simple translations (Uses the django language)
```html
<p>
    {% i18n_switch "hello" %}
</p>
```

### 2. Template tag example with custom language:
```html
<p>
    {% i18n_switch "hello" "sv" %}
</p>
```

### 3. Template tag example with values

#### Passed view context:
```python
	context = {
		'values': {
			'name': 'John Doe'
		}
	}

```

#### Your translation at www.i18nize.com:
`"Hello {{name}}!"`

#### Inside your django template:
```html
<p>
    {% i18n_switch "greet_person" "en" values %}
</p>
```