Sail CRM Booking API
====

Lightweight JSON API for sail-croatia booking CRM.

## Installation



## API (beta)

API need access token, email to info@sailcroatia.com to get token

Get all cruises:

    https://dev-sailcrm.herokuapp.com/api/v1/cruises

JSON result:

    {"cruises":[
        {"id":3,"name":"Elegance Cruise","numberOfDays":8},
        {"id":9,"name":"Special - Green Sail Cruise","numberOfDays":8}
    ],
        "status":200
    }
    
Get all directions by cruise id:

    https://dev-sailcrm.herokuapp.com/api/v1/cruises/:id/directions

  JSON result:

    {"directions":[
        {"id":62,"name":"Dubrovnik - Split"},
        {"id":63,"name":"Split - Dubrovnik"}
    ],
    "status":200
    }


Get all tours by directions id:

    https://dev-sailcrm.herokuapp.com/api/v1/directions/:id/tours
    
JSON result:

    {"tours":[
        {"id":696,"departure":"2016-08-14T00:00:00.000Z"},
        {"id":710,"departure":"2016-10-02T00:00:00.000Z"}
    ],
    "status":200
    }

Get all ships by tour id:

    https://dev-sailcrm.herokuapp.com/api/v1/tours/:id/ships
    
JSON result:

    {"ships":[
        {"id":"Premier Plus/Above Deck/1299.0","name":"Premier Plus - Above Deck - \u0026pound;1299"},
        {"id":"Premier Plus/Lower Deck/1149.0","name":"Premier Plus - Lower Deck - \u0026pound;1149"}
    ],
        "status":200
    }
    
Create enquiry:

    https://dev-sailcrm.herokuapp.com/api/v1/enquiry

## Example (curl)

#### GET:

     curl -H "Authorization: Token token=user_token" https://dev-sailcrm.herokuapp.com/api/v1/cruises

#### POST:

    curl -H "Authorization: Token token=user_token" -d "customer[title]=Mr&customer[first_name]=Nilanga&customer[last_name]=Saluwadana&customer[birth_year]=1986&customer[email]=nilanga89@gmail.com&customer[confirm_email]=nilanga89@gmail.com&customer[country_code]=New Zealand_+64&customer[tel]=0772939096&customer[nationality]=New Zealander&enquiry[pax]=20&enquiry[cruise_id]=1&enquiry[direction_id]=62&enquiry[tour_id]=696&enquiry[ship]=Premier Plus/Above Deck/1299.0&enquiry[note]=Addition information" -X POST https://dev-sailcrm.herokuapp.com/api/v1/enquiry

## Example (Ajax)

#### GET:

     $.getJSON("https://dev-sailcrm.herokuapp.com/api/v1/cruises", function(data) {
            $.each( data.cruises, function( key, val ) {
               console.log(val.id+" "+val.name)
            });
     });

#### POST JSON request:

    jQuery.ajax({
      type: 'POST',
      url: 'https://dev-sailcrm.herokuapp.com/api/v1/enquiry',
      dataType: 'json',
      contentType: 'application/json',
      data: JSON.stringify({ customer: { first_name: "Yehuda", last_name: "Katz" } }),
      success: function(json) {
        console.log(json)
      }
    });
    
#### POST without JSON request:

    jQuery.ajax({
      type: 'POST',
      url: 'https://dev-sailcrm.herokuapp.com/api/v1/enquiry',
      dataType: 'json',
      data: $("#booking").serialize(),
      success: function(json) {
          console.log(json)
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
