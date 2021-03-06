# README

## minimal rails new

```shell
rails new --database=sqlite3 --skip-action-mailer --skip-action-mailbox --skip-action-text --skip-active-job --skip-active-storage --skip-action-cable --skip-javascript --skip-hotwire --skip-jbuilder --skip-test --skip-system-test --skip-bootsnap --minimal .
```

## Gemfile for rubocop

```Gemfile
  gem 'rubocop'
  gem 'rubocop-ast'
  gem 'rubocop-performance'
  gem 'rubocop-rails'
  gem 'rubocop-rake'
  gem 'rubocop-rspec'
```

`.rubocop.yml`

```yaml
inherit_from: .rubocop_todo.yml

Style/AsciiComments:
  Enabled: false

Style/Documentation:
  Enabled: false

AllCops:
  TargetRubyVersion: 3.1
  NewCops: enable

require:
  - rubocop-ast
  - rubocop-rails
  - rubocop-rake
  - rubocop-rspec
  - rubocop-performance

```

and blank `.rubocop_todo.yml`

## Apply autocorrect of rubcop

```shell
rubocop -a
```

## Gemfile for erb_lint

```Gemfile
  gem 'erb_lint'
```

`.erb-lint.yml`

```yaml
EnableDefaultLinters: true
linters:
  Rubocop:
    enabled: true
    rubocop_config:
      inherit_from:
        - .rubocop.yml
      Style/FrozenStringLiteralComment:
        Enabled: false
      Layout/InitialIndentation:
        Enabled: false
      Layout/TrailingEmptyLines:
        Enabled: false
```

## Apply autocorrect of erb_lint

```shell
erblint --lint-all -a
```

