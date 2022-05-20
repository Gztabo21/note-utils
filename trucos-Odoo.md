# trucos  - odoo 
## Eliminar action duplicado.
```
<record id="view_form_id" model="ir.ui.view">
  <field name="name">view name</field>
  <field name="model">my.model</field>
  <field name="priority" eval="10"/>
  <field name="arch" type="xml">
     <form string="..." duplicate="0">
     ...
     </form>
  </field>
</record>
```

Try to add 

```<form string="..." duplicate="0">```

(0, 0,  { values })    link to a new record that needs to be created with the given values dictionary
(1, ID, { values })    update the linked record with id = ID (write *values* on it)
(2, ID)                remove and delete the linked record with id = ID (calls unlink on ID, that will delete the object completely, and the link to it as well)
(3, ID)                cut the link to the linked record with id = ID (delete the relationship between the two objects but does not delete the target object itself)
(4, ID)                link to existing record with id = ID (adds a relationship)
(5)                    unlink all (like using (3,ID) for all linked records)
(6, 0, [IDs])          replace the list of linked IDs (like using (5) then (4,ID) for each ID in the list of IDs)

## eliminar add line 
``` <tree string="my Tree" create="false"> ```
## campos optinales en la vista tree
 ```<field name="field_name" optinal="hide"/>```
## Eliminar modulo por consola 
Entrar al terminal.
> odoo 15
```update ir_module_module set state='uninstalled' where name='name_module' and state='installed';```
```delete from ir_model_data where name like '%name_module%';```
```delete from ir_model_access where name like '%name_module%';```
# QWEB
```&gt;``` es igual al >
```&lt;``` es igual al <
