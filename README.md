Sail CRM Booking API
====

Lightweight JSON API for sail-croatia booking CRM.

## Installation



## API ( beta ) 

Get all cruises:

    https://dev-sailcrm.herokuapp.com/api/v1/cruises

Get all Directions by cruise id:

    https://dev-sailcrm.herokuapp.com/api/v1/cruises/:id/directions

Get all tours by directions id:

    https://dev-sailcrm.herokuapp.com/api/v1/directions/:id/tours

Get all ships by tour id:

    https://dev-sailcrm.herokuapp.com/api/v1/tours/:id/ships

Create enquiry:

    https://dev-sailcrm.herokuapp.com/api/v1/enquiry

## Example

curl :

     var validator = new Dominar($('#new_user'), {
            "user[name]": {
                rules: 'required|min:3|max:10'
            },
            "user[notes]": {
                rules: 'required|min:5|max:20'
            },
            "user[group]": {
                rules: 'required|in:guest,admin'
            }
     });


## Versions

This is beta version

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
