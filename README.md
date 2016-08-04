# Reference
Defines a field type to let entities referencing other entites in Backdrop.

Note: this module is currently under development and should not be used on any production sites.

### Current status:

Autocomple widget does not work, and needs to be changed to use new entity type bundle combos.

### Completed:

* define the field in reference_field_info()
* define the field schema in reference_field_schema()
* alter node entity info to provide its label and status properties
* create global and instace settings forms for the field
* define reference_field_is_empty() to check whether the field is filled in or not
* define a reference_autocomplete widget in hook_field_widget_info
* define a widget form in reference_field_widget_form (though not actually autocomplete yet)
* define a simple link display formatter in reference_field_formatter_info
* render a link to the referenced entity in reference_field_formatter_view
* use a select list for the entity type in the widget that respect the type restriction
* field validation to make sure the referenced entity exists
* define automcomplete function to make autocomplete widget actually autocomplete
* function to turn the autocomplete value to a numberic target id on form submit
* switch to using entity type bundle combos that are allowed to be referenced

### In progress:

* add js file for widget
* change autocomplete function to use new entity/bundle combo
* switch autocomplete path for entity_id when entity_type changes
* clear entity id field if the entity type is changed

### Things to do:

* update reference_entity_info_alter to provide info on all core entities
* check that entity exists in autocomplete validate
* get autocomplete function to respect status restrictions
* permissions on autocomplete callback to check that user has ability to edit the field
* update field validation to test that the referenced entity meets restrictions
* hide or disable entity type selector if only one entity type can be selected
* hide the numeric id from the user after autocomplete select?
* autocomplete to get entity labels that start with the typed text before just containing
* error or watchdog when trying to reference an entity that hasn't defined its keys properly
* additional field formatter to display rendered entity
* views integration
* mutilingual support for label autocomplete
* and many more...

### To merge into core:

* write tests
* patch core modules to provide their label and status properties in their entity info
* remove then-unneeded reference_entity_info_alter() function
* replace references provided by other core modules, such as taxonomy tags and other term refs
* upgrade path from taxonomy reference modules
* upgrade path from contrib references to reference?
* standardized autocomplete widget?
