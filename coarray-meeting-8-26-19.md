# Coarray Meeting
Notes from brief call on 8.26.2019, discussing on what to present to the Wednesday f18 call.

Create slides on the following:

## rough f18 coarray development plan

### coarray subroutines that don't need arguments
These will be trivial to map over. Later make sure arguments work
** this_images()
** num_images()
** sync_images()
** etc.

### collective subroutines
** co_broadcast
** co_max
** co_min
** co_sum
* teams
todo: Need to figure out data structure for holding teams.
      Will open coarray library hold info about teams or f18?

### coarrays
** start with allocation
During memory allocation for coarray, descriptor (caf_token_t) gets created
Handeling memory allocation goes to coarrays,
Pass caf token to F18 and they'll store that, they'll need it for calling caf_get, caf_put etc.
Good resource on API calls https://gcc.gnu.org/onlinedocs/gcc-7.2.0/gfortran/Function-ABI-Documentation.html

# remaining questions
When do we lower coarray information, soon or later?
What will f18 want to store?
 * caf_token_t (naturally)
 * this_image, (this will change depending on teams? -scr)
