list
====

This code should compile everywhere and survive to all warning flags (*).

(*) Almost

## Build ##

To build the library, use:

	$ make

## Example ##

The following example shows how to use a singly linked list:

	#include "list.h"

	typedef struct person_s {
	  /* This must be first */
	  struct person_s *next;
	  int id;
	} person_t;

	/* Always initialize a list to NULL */
	person_t *list = NULL;
	
	person_t *person = calloc(1, sizeof(person_t));
	person->id = 0;

	list = (person_t *)l_push((list_t *)list, (list_t *)person);
	assert(l_size((list_t *)list) == 1);

	list = (person_t *)l_free((list_t *)list, NULL);
