Sail CRM Booking API
====

Lightweight JSON API for sail-croatia booking CRM.

## Installation



## API (beta)

API need access token, email to info@sailcroatia.com to get token

Get all cruises:

    https://dev-sailcrm.herokuapp.com/api/v1/cruises

Get all directions by cruise id:

    https://dev-sailcrm.herokuapp.com/api/v1/cruises/:id/directions

Get all tours by directions id:

    https://dev-sailcrm.herokuapp.com/api/v1/directions/:id/tours

Get all ships by tour id:

    https://dev-sailcrm.herokuapp.com/api/v1/tours/:id/ships

Create enquiry:

    https://dev-sailcrm.herokuapp.com/api/v1/enquiry

## Example
### curl
GET:

     curl -H "Authorization: Token token=user_token" https://dev-sailcrm.herokuapp.com/api/v1/cruises

POST:

    curl -H "Authorization: Token token=user_token" -d "customer[title]=Mr&customer[first_name]=Nilanga&customer[last_name]=Saluwadana&customer[birth_year]=1986&customer[email]=nilanga89@gmail.com&customer[confirm_email]=nilanga89@gmail.com&customer[country_code]=New Zealand_+64&customer[tel]=0772939096&customer[nationality]=New Zealander&enquiry[pax]=20&enquiry[cruise_id]=1&enquiry[direction_id]=62&enquiry[tour_id]=696&enquiry[ship]=Premier Plus/Above Deck/1299.0&enquiry[note]=Addition information" -X POST https://dev-sailcrm.herokuapp.com/api/v1/enquiry

### Ajax

GET:

     curl -H "Authorization: Token token=user_token" https://dev-sailcrm.herokuapp.com/api/v1/cruises

POST:

    curl -H "Authorization: Token token=user_token" -d "customer[title]=Mr&customer[first_name]=Nilanga&customer[last_name]=Saluwadana&customer[birth_year]=1986&customer[email]=nilanga89@gmail.com&customer[confirm_email]=nilanga89@gmail.com&customer[country_code]=New Zealand_+64&customer[tel]=0772939096&customer[nationality]=New Zealander&enquiry[pax]=20&enquiry[cruise_id]=1&enquiry[direction_id]=62&enquiry[tour_id]=696&enquiry[ship]=Premier Plus/Above Deck/1299.0&enquiry[note]=Addition information" -X POST https://dev-sailcrm.herokuapp.com/api/v1/enquiry


## Versions

This is beta version

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
