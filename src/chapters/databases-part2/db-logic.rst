Database Functions
==================

#. Import required modules.
#. Review the execute_query() function.
#. Code record_mines() and count_mines() functions.
#. Code the check_surroundings() function. Note the *nested* loops for the
   systematic row and column checks.

Note counter in record_mines. This works for now, since the list of mine coords
is sorted, and the rows are added to the mine table in order. However, if we
wanted to link these two tables, or if the mines were added to existing
content, we would need to add extra steps to match the mine_id values in the
separate tables.

Video tutorial...
