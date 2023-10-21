# ActiveAdmin::JsonEditor

"json_input" and "jsonb_input" field type to ActiveAdmin that allow you to edit PostgreSQL json and
jsonb values as a JSON tree.

Data is shown using the jsoneditor.js from http://jsoneditoronline.org

## Installation

Add this line to your application's Gemfile:

    gem 'activeadmin_json_editor', github: 'ninjasonmars/activeadmin_json_editor'

And then execute:

    $ bundle

Include the styles and scripts in the "active_admin" initializer:

    config.register_stylesheet 'active_admin/json_editor.css'
    config.register_javascript 'active_admin/json_editor.js'

## Usage

This Gem provides you a Formtastic input called `:json` to edit JSON data and parse form data to
store it properly in the database.

```ruby
ActiveAdmin.register User do
  permit_params :settings

  json_editor

  form do |f|
    f.inputs do
      f.input :settings, as: :json
      f.input :other_settings, as: :jsonb
    end

    f.actions
  end
end
```
