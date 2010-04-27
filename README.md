CountrySelect
=============

Provides a simple helper to get an HTML select list of countries.  The list of countries comes from an ActiveRecord model.

Based on the original work of Michael Koziarski which used a constant for the country names.

Example
=======

The plugin defaults to using the "Country" model with field "Name". Override COUNTRY_SELECT_MODEL_NAME and COUNTRY_SELECT_MODEL_FIELD for different behavior.

    country_select("user", "country_name")

Use the form helper to create a selector for countries with a set of priority countries that should show up at the top of the list.

    form_for @user do |form|
      form.country_select :province, Country.priority_countries
    end

Changelog
=========

* 4/27/2010 - Priority countries are now passed as an array of objects that respond to #id and #name. Used to accept a simple array of strings that were looked up in the db individually (slow)

Copyright (c) 2010 Tim Harvey, released under the MIT license
