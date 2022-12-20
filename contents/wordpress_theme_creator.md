# Wordpress

## Create a classic template

1. Edit the wp-config.php
2. Change `define( 'WP_DEBUG', false );` to:

| Bash |
| ---- |
| `define( 'WP_DISABLE_FATAL_ERROR_HANDLER', true );` |
| `define( 'WP_DEBUG', true );` |
| `define( 'WP_DEBUG_LOG', true );` |
| `define( 'WP_DEBUG_DISPLAY', true );` |

3. If necessary, download test content in [Theme Unit Test](https://codex.wordpress.org/Theme_Unit_Test). Like this:

| Bash |
| ---- |
| `curl https://raw.githubusercontent.com/WPTT/theme-unit-test/master/themeunittestdata.wordpress.xml > theme_unit_test.xml` |

4. No painel do Wordpress vá em `Tools => Import => WordPress => Install now`
5. Select the XML file from your computer
6. 
