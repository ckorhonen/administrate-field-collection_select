# Repository Guide

- This is a Ruby gem extending Administrate collection-select fields; the gemspec and `lib/` define the public package.
- Use Bundler to install dependencies and `bundle exec rake` for the default RSpec task. The Rake task is declared, but no spec files or Appraisals are checked in; a zero-example result is not behavior coverage.

`lib/administrate/field/collection_select.rb` defines the field; `app/views/fields/collection_select/` contains form/show/index partials. Run commands at the root. The legacy `.ruby-version` and Travis config select Ruby 2.4/Bundler 1.14, while the gemspec now requires Rails ~>6.0; that Rails dependency requires a newer Ruby than the pin. Resolve and report this toolchain mismatch within the task before relying on `bundle install`; do not silently rewrite compatibility policy or claim the pinned setup works.

For changed Ruby, `ruby -c lib/administrate/field/collection_select.rb` is syntax-only. Add focused specs when behavior changes and run the declared `bundle exec rake` after prerequisites are resolved. Partial/UI changes need an available compatible consuming Administrate app to inspect form and display behavior; missing host integration is an explicit validation limit. Preserve the field API and unrelated work, and report actual example counts and any unverified Rails compatibility.
