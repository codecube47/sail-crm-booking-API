Sail CRM Booking API
====

Lightweight JSON API for sail-croatia booking CRM.

## Installation



## API (beta)

API Access token, email to info@sailcroatia.com

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
    
JSON result:

    {"message":"Enquiry created","status":201}

## Example (curl)

#### GET:

     curl -H "Authorization: Token token=user_token" https://dev-sailcrm.herokuapp.com/api/v1/cruises

#### POST:

    curl -H "Authorization: Token token=user_token" -d "customer[title]=Mr&customer[first_name]=Nilanga&customer[last_name]=Saluwadana&customer[birth_year]=1986&customer[email]=nilanga89@gmail.com&customer[confirm_email]=nilanga89@gmail.com&customer[country_code]=New Zealand_+64&customer[tel]=0772939096&customer[nationality]=New Zealander&enquiry[pax]=20&enquiry[cruise_id]=1&enquiry[direction_id]=62&enquiry[tour_id]=696&enquiry[ship]=Premier Plus/Above Deck/1299.0&enquiry[note]=Addition information" -X POST https://dev-sailcrm.herokuapp.com/api/v1/enquiry

## Example (ajax)

Setup Authorization

        $.ajaxSetup({
            headers: {
                'Authorization': "Token token=your_token"
            }
        });


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

#### Sample HTML from:

    <form accept-charset="UTF-8" action="/" method="post" id="booking">
    <div class="row" >
        <div class="col-md-4 6 col-md-offset-4">
        <div class="form-group">
            <label for="customer_title">Title*</label><br>
            <select class="form-control" id="customer_title" name="customer[title]">
                <option value="">Select</option>
                <option value="Mr">Mr</option>
                <option value="Mrs">Mrs</option>
                <option value="Ms">Ms</option>
                <option value="Miss">Miss</option>
            </select>
        </div>

        <div class="form-group">
            <label for="customer_first_name">First Name*</label>
            <input class="form-control" id="customer_first_name" name="customer[first_name]" type="text">
        </div>

        <div class="form-group">
            <label for="customer_last_name">Last Name*</label>
            <input class="form-control" id="customer_last_name" name="customer[last_name]" type="text">
        </div>

        <div class="form-group">
            <label for="customer_birth_year">Birth Year*</label><br>
            <select class="form-control" id="customer_birth_year" name="customer[birth_year]">
                <option value="">Select</option>
                <option value="1998">1998</option><option value="1997">1997</option><option value="1996">1996</option><option value="1995">1995</option><option value="1994">1994</option><option value="1993">1993</option><option value="1992">1992</option><option value="1991">1991</option><option value="1990">1990</option><option value="1989">1989</option><option value="1988">1988</option><option value="1987">1987</option><option value="1986">1986</option><option value="1985">1985</option><option value="1984">1984</option><option value="1983">1983</option><option value="1982">1982</option><option value="1981">1981</option><option value="1980">1980</option><option value="1979">1979</option><option value="1978">1978</option><option value="1977">1977</option><option value="1976">1976</option><option value="1975">1975</option><option value="1974">1974</option><option value="1973">1973</option><option value="1972">1972</option><option value="1971">1971</option><option value="1970">1970</option><option value="1969">1969</option><option value="1968">1968</option><option value="1967">1967</option><option value="1966">1966</option><option value="1965">1965</option><option value="1964">1964</option><option value="1963">1963</option><option value="1962">1962</option><option value="1961">1961</option><option value="1960">1960</option><option value="1959">1959</option><option value="1958">1958</option><option value="1957">1957</option><option value="1956">1956</option><option value="1955">1955</option><option value="1954">1954</option><option value="1953">1953</option><option value="1952">1952</option><option value="1951">1951</option><option value="1950">1950</option><option value="1949">1949</option><option value="1948">1948</option><option value="1947">1947</option><option value="1946">1946</option><option value="1945">1945</option><option value="1944">1944</option><option value="1943">1943</option><option value="1942">1942</option><option value="1941">1941</option><option value="1940">1940</option><option value="1939">1939</option><option value="1938">1938</option><option value="1937">1937</option><option value="1936">1936</option>
            </select>
        </div>

        <div class="form-group">
            <label for="customer_email">Email*</label>
            <input class="form-control" id="customer_email" name="customer[email]" type="text">
        </div>

        <div class="form-group">
            <label for="confirm_email">Confirm Email*</label>
            <input class="form-control" id="confirm_email" name="customer[confirm_email]" type="text">
        </div>

        <div class="form-group">
            <label for="customer_country_code">Country Code*</label>
            <select name="customer[country_code]" id="customer_country_code" class="form-control"><option value="">Select Your Country Code</option><option value="Australia_+61">Australia (+61)</option><option value="Canada_+1">Canada (+1)</option><option value="New Zealand_+64">New Zealand (+64)</option><option value="South Africa_+27">South Africa (+27)</option><option value="United Kingdom_+44">United Kingdom (+44)</option><option value="United States Of America_+1">United States Of America (+1)</option><option value="">-----------------</option><option value="Afghanistan_+93">Afghanistan (+93)</option><option value="Albania_+355">Albania (+355)</option><option value="Algeria_+213">Algeria (+213)</option><option value="American Samoa_+684">American Samoa (+684)</option><option value="Andorra_+376">Andorra (+376)</option><option value="Angola_+244">Angola (+244)</option><option value="Anguilla_+264">Anguilla (+264)</option><option value="Antarctica_+672">Antarctica (+672)</option><option value="Antigua And Barbuda_+268">Antigua And Barbuda (+268)</option><option value="Argentina_+54">Argentina (+54)</option><option value="Armenia_+374">Armenia (+374)</option><option value="Aruba_+297">Aruba (+297)</option><option value="Australia_+61">Australia (+61)</option><option value="Austria_+43">Austria (+43)</option><option value="Azerbaijan_+994">Azerbaijan (+994)</option><option value="Bahamas_+242">Bahamas (+242)</option><option value="Bahrain_+973">Bahrain (+973)</option><option value="Bangladesh_+880">Bangladesh (+880)</option><option value="Barbados_+246">Barbados (+246)</option><option value="Belarus_+375">Belarus (+375)</option><option value="Belgium_+32">Belgium (+32)</option><option value="Belize_+501">Belize (+501)</option><option value="Benin_+229">Benin (+229)</option><option value="Bermuda_+441">Bermuda (+441)</option><option value="Bhutan_+975">Bhutan (+975)</option><option value="Bolivia_+591">Bolivia (+591)</option><option value="Bosnia And Herzegovina_+387">Bosnia And Herzegovina (+387)</option><option value="Botswana_+267">Botswana (+267)</option><option value="Brazil_+55">Brazil (+55)</option><option value="Brunei Darussalam_+673">Brunei Darussalam (+673)</option><option value="Bulgaria_+359">Bulgaria (+359)</option><option value="Burkina Faso_+226">Burkina Faso (+226)</option><option value="Burundi_+257">Burundi (+257)</option><option value="Cambodia_+855">Cambodia (+855)</option><option value="Cameroon_+237">Cameroon (+237)</option><option value="Canada_+1">Canada (+1)</option><option value="Cape Verde_+238">Cape Verde (+238)</option><option value="Cayman Islands_+345">Cayman Islands (+345)</option><option value="Central African Republic_+236">Central African Republic (+236)</option><option value="Chad_+235">Chad (+235)</option><option value="Channel Islands_+44">Channel Islands (+44)</option><option value="Chile_+56">Chile (+56)</option><option value="China (Peoples Republic)_+86">China (Peoples Republic) (+86)</option><option value="Christmas Island_+61">Christmas Island (+61)</option><option value="Cocos Keeling Islands_+61">Cocos Keeling Islands (+61)</option><option value="Colombia_+57">Colombia (+57)</option><option value="Comoros_+269">Comoros (+269)</option><option value="Congo (Former Zaire)_+243">Congo (Former Zaire) (+243)</option><option value="Congo (Republic Of)_+242">Congo (Republic Of) (+242)</option><option value="Cook Islands_+682">Cook Islands (+682)</option><option value="Costa Rica_+506">Costa Rica (+506)</option><option value="Cote Divoire (Ivory Coast)_+225">Cote Divoire (Ivory Coast) (+225)</option><option value="Croatia (Hrvatska)_+385">Croatia (Hrvatska) (+385)</option><option value="Cuba_+53">Cuba (+53)</option><option value="Cyprus_+357">Cyprus (+357)</option><option value="Czech Republic_+420">Czech Republic (+420)</option><option value="Denmark_+45">Denmark (+45)</option><option value="Djibouti_+253">Djibouti (+253)</option><option value="Dominica_+767">Dominica (+767)</option><option value="Dominican Republic_+809">Dominican Republic (+809)</option><option value="Ecuador_+593">Ecuador (+593)</option><option value="Egypt_+20">Egypt (+20)</option><option value="El Salvador_+503">El Salvador (+503)</option><option value="Equatorial Guinea_+240">Equatorial Guinea (+240)</option><option value="Eritrea_+291">Eritrea (+291)</option><option value="Estonia_+372">Estonia (+372)</option><option value="Ethiopia_+251">Ethiopia (+251)</option><option value="Falkland Islands (Malvinas)_+500">Falkland Islands (Malvinas) (+500)</option><option value="Faroe Islands_+298">Faroe Islands (+298)</option><option value="Fiji_+679">Fiji (+679)</option><option value="Finland_+358">Finland (+358)</option><option value="France_+33">France (+33)</option><option value="Freetext Country_+33">Freetext Country (+33)</option><option value="French Guiana_+594">French Guiana (+594)</option><option value="French Polynesia_+689">French Polynesia (+689)</option><option value="Gabon_+241">Gabon (+241)</option><option value="Gambia_+220">Gambia (+220)</option><option value="Georgia_+995">Georgia (+995)</option><option value="Germany_+49">Germany (+49)</option><option value="Ghana_+233">Ghana (+233)</option><option value="Gibraltar_+350">Gibraltar (+350)</option><option value="Greece_+30">Greece (+30)</option><option value="Greenland_+299">Greenland (+299)</option><option value="Grenada_+473">Grenada (+473)</option><option value="Guadeloupe_+590">Guadeloupe (+590)</option><option value="Guam_+670">Guam (+670)</option><option value="Guatemala_+502">Guatemala (+502)</option><option value="Guernsey_+44">Guernsey (+44)</option><option value="Guinea_+224">Guinea (+224)</option><option value="Guinea-Bissau_+245">Guinea-Bissau (+245)</option><option value="Guyana_+592">Guyana (+592)</option><option value="Haiti_+509">Haiti (+509)</option><option value="Honduras_+504">Honduras (+504)</option><option value="Hong Kong_+852">Hong Kong (+852)</option><option value="Hungary_+36">Hungary (+36)</option><option value="Iceland_+354">Iceland (+354)</option><option value="India_+91">India (+91)</option><option value="Indonesia_+62">Indonesia (+62)</option><option value="Iran_+98">Iran (+98)</option><option value="Iraq_+964">Iraq (+964)</option><option value="Ireland_+353">Ireland (+353)</option><option value="Israel_+972">Israel (+972)</option><option value="Italy_+39">Italy (+39)</option><option value="Jamaica_+876">Jamaica (+876)</option><option value="Japan_+81">Japan (+81)</option><option value="Jersey_+44">Jersey (+44)</option><option value="Jordan_+962">Jordan (+962)</option><option value="Kazakhstan_+7">Kazakhstan (+7)</option><option value="Kenya_+254">Kenya (+254)</option><option value="Kiribati_+686">Kiribati (+686)</option><option value="Kuwait_+965">Kuwait (+965)</option><option value="Kyrgyzstan_+996">Kyrgyzstan (+996)</option><option value="Laos_+856">Laos (+856)</option><option value="Latvia_+371">Latvia (+371)</option><option value="Lebanon_+961">Lebanon (+961)</option><option value="Lesotho_+266">Lesotho (+266)</option><option value="Liberia_+231">Liberia (+231)</option><option value="Libya Arab Jamahiriya_+218">Libya Arab Jamahiriya (+218)</option><option value="Liechtenstein_+423">Liechtenstein (+423)</option><option value="Lithuania_+370">Lithuania (+370)</option><option value="Luxembourg_+352">Luxembourg (+352)</option><option value="Macau (Sar) China_+853">Macau (Sar) China (+853)</option><option value="Macedonia (Fyrom)_+389">Macedonia (Fyrom) (+389)</option><option value="Madagascar_+261">Madagascar (+261)</option><option value="Malawi_+265">Malawi (+265)</option><option value="Malaysia_+60">Malaysia (+60)</option><option value="Maldives_+960">Maldives (+960)</option><option value="Mali_+223">Mali (+223)</option><option value="Malta_+356">Malta (+356)</option><option value="Marshall Islands_+692">Marshall Islands (+692)</option><option value="Martinique_+596">Martinique (+596)</option><option value="Mauritania_+222">Mauritania (+222)</option><option value="Mauritius_+230">Mauritius (+230)</option><option value="Mayotte_+269">Mayotte (+269)</option><option value="Mexico_+52">Mexico (+52)</option><option value="Micronesia_+691">Micronesia (+691)</option><option value="Moldova (Republic Of)_+373">Moldova (Republic Of) (+373)</option><option value="Monaco_+377">Monaco (+377)</option><option value="Mongolia_+976">Mongolia (+976)</option><option value="Montenegro_+382">Montenegro (+382)</option><option value="Montserrat_+664">Montserrat (+664)</option><option value="Morocco_+212">Morocco (+212)</option><option value="Mozambique_+258">Mozambique (+258)</option><option value="Myanmar_+95">Myanmar (+95)</option><option value="Namibia_+264">Namibia (+264)</option><option value="Nauru_+674">Nauru (+674)</option><option value="Nepal_+977">Nepal (+977)</option><option value="Netherlands_+31">Netherlands (+31)</option><option value="Netherlands Antilles_+599">Netherlands Antilles (+599)</option><option value="New Caledonia_+687">New Caledonia (+687)</option><option value="New Zealand_+64">New Zealand (+64)</option><option value="Nicaragua_+505">Nicaragua (+505)</option><option value="Niger_+227">Niger (+227)</option><option value="Nigeria_+234">Nigeria (+234)</option><option value="Niue_+683">Niue (+683)</option><option value="Norfolk Island_+672">Norfolk Island (+672)</option><option value="North Korea_+850">North Korea (+850)</option><option value="Northern Mariana Islands_+1670">Northern Mariana Islands (+1670)</option><option value="Norway_+47">Norway (+47)</option><option value="Oman_+968">Oman (+968)</option><option value="Open_+99">Open (+99)</option><option value="Pakistan_+92">Pakistan (+92)</option><option value="Palau_+680">Palau (+680)</option><option value="Palestine_+972">Palestine (+972)</option><option value="Panama_+507">Panama (+507)</option><option value="Papua New Guinea_+675">Papua New Guinea (+675)</option><option value="Paraguay_+595">Paraguay (+595)</option><option value="Peru_+51">Peru (+51)</option><option value="Philippines_+63">Philippines (+63)</option><option value="Poland_+48">Poland (+48)</option><option value="Portugal_+351">Portugal (+351)</option><option value="Puerto Rico_+787">Puerto Rico (+787)</option><option value="Qatar_+974">Qatar (+974)</option><option value="Reunion_+262">Reunion (+262)</option><option value="Romania_+40">Romania (+40)</option><option value="Russian Federation_+7">Russian Federation (+7)</option><option value="Rwanda_+250">Rwanda (+250)</option><option value="Samoa_+685">Samoa (+685)</option><option value="San Marino_+378">San Marino (+378)</option><option value="Sao Tome And Principe_+239">Sao Tome And Principe (+239)</option><option value="Saudi Arabia_+966">Saudi Arabia (+966)</option><option value="Senegal_+221">Senegal (+221)</option><option value="Serbia_+381">Serbia (+381)</option><option value="Seychelles_+248">Seychelles (+248)</option><option value="Sierra Leone_+232">Sierra Leone (+232)</option><option value="Singapore_+65">Singapore (+65)</option><option value="Slovakia_+421">Slovakia (+421)</option><option value="Slovenia_+386">Slovenia (+386)</option><option value="Solomon Islands_+677">Solomon Islands (+677)</option><option value="Somalia_+252">Somalia (+252)</option><option value="South Africa_+27">South Africa (+27)</option><option value="South Korea_+82">South Korea (+82)</option><option value="Spain_+34">Spain (+34)</option><option value="Sri Lanka_+94">Sri Lanka (+94)</option><option value="St Helena_+290">St Helena (+290)</option><option value="St Kitts-Nevis_+869">St Kitts-Nevis (+869)</option><option value="St Lucia_+758">St Lucia (+758)</option><option value="St Pierre And Miquelon_+508">St Pierre And Miquelon (+508)</option><option value="Sudan_+249">Sudan (+249)</option><option value="Suriname_+597">Suriname (+597)</option><option value="Swaziland_+268">Swaziland (+268)</option><option value="Sweden_+46">Sweden (+46)</option><option value="Switzerland_+41">Switzerland (+41)</option><option value="Syrian Arab Republic_+963">Syrian Arab Republic (+963)</option><option value="Taiwan Chinese Taipai_+886">Taiwan Chinese Taipai (+886)</option><option value="Tajikistan_+7">Tajikistan (+7)</option><option value="Tanzania (United Republic Of)_+255">Tanzania (+255)</option><option value="Thailand_+66">Thailand (+66)</option><option value="Togo_+228">Togo (+228)</option><option value="Tonga_+676">Tonga (+676)</option><option value="Trinidad And Tobago_+868">Trinidad And Tobago (+868)</option><option value="Tunisia_+216">Tunisia (+216)</option><option value="Turkey_+90">Turkey (+90)</option><option value="Turkmenistan_+993">Turkmenistan (+993)</option><option value="Turks And Caicos Islands_+649">Turks And Caicos Islands (+649)</option><option value="Tuvalu_+688">Tuvalu (+688)</option><option value="Uganda_+256">Uganda (+256)</option><option value="Ukraine_+380">Ukraine (+380)</option><option value="United Arab Emirates_+971">United Arab Emirates (+971)</option><option value="United Kingdom_+44">United Kingdom (+44)</option><option value="United States Of America_+1">United States Of America (+1)</option><option value="Uruguay_+598">Uruguay (+598)</option><option value="Uzbekistan_+998">Uzbekistan (+998)</option><option value="Vanuatu_+678">Vanuatu (+678)</option><option value="Venezuela_+58">Venezuela (+58)</option><option value="Vietnam_+84">Vietnam (+84)</option><option value="Virgin Islands (British)_+248">Virgin Islands (British) (+248)</option><option value="Virgin Islands (US)_+1">Virgin Islands (US) (+1)</option><option value="Wallis And Futuna Islands_+681">Wallis And Futuna Islands (+681)</option><option value="Yemen_+967">Yemen (+967)</option><option value="Zambia_+260">Zambia (+260)</option><option value="Zimbabwe_+263">Zimbabwe (+263)</option></select>
        </div>

        <div class="form-group">
            <label for="customer_tel">Contact Number*</label>
            <input class="form-control" id="customer_tel" name="customer[tel]" type="text">
        </div>

        <div class="form-group">
            <label for="customer_nationality">Nationality*</label>
            <select name="customer[nationality]" id="customer_nationality" class="form-control"><option value="">Select your Nationality</option><option value="Australian">Australian</option><option value="Canadian">Canadian</option><option value="New Zealander">New Zealander</option><option value="South African">South African</option><option value="British">British</option><option value="American">American</option><option value="">--------------------------</option><option value="Afghan">Afghan</option> <option value="Albanian">Albanian</option> <option value="Algerian">Algerian</option> <option value="American">American</option> <option value="Andorran">Andorran</option> <option value="Angolan">Angolan</option> <option value="Antiguans">Antiguans</option> <option value="Argentinean">Argentinean</option> <option value="Armenian">Armenian</option> <option value="Australian">Australian</option> <option value="Austrian">Austrian</option> <option value="Azerbaijani">Azerbaijani</option> <option value="Bahamian">Bahamian</option> <option value="Bahraini">Bahraini</option> <option value="Bangladeshi">Bangladeshi</option> <option value="Barbadian">Barbadian</option> <option value="Barbudans">Barbudans</option> <option value="Batswana">Batswana</option> <option value="Belarusian">Belarusian</option> <option value="Belgian">Belgian</option> <option value="Belizean">Belizean</option> <option value="Beninese">Beninese</option> <option value="Bhutanese">Bhutanese</option> <option value="Bolivian">Bolivian</option> <option value="Bosnian">Bosnian</option> <option value="Brazilian">Brazilian</option> <option value="British">British</option> <option value="Bruneian">Bruneian</option> <option value="Bulgarian">Bulgarian</option> <option value="Burkinabe">Burkinabe</option> <option value="Burmese">Burmese</option> <option value="Burundian">Burundian</option> <option value="Cambodian">Cambodian</option> <option value="Cameroonian">Cameroonian</option> <option value="Canadian">Canadian</option> <option value="Cape Verdean">Cape Verdean</option> <option value="Central African">Central African</option> <option value="Chadian">Chadian</option> <option value="Chilean">Chilean</option> <option value="Chinese">Chinese</option> <option value="Colombian">Colombian</option> <option value="Comoran">Comoran</option> <option value="Congolese">Congolese</option> <option value="Costa Rican">Costa Rican</option> <option value="Croatian">Croatian</option> <option value="Cuban">Cuban</option> <option value="Cypriot">Cypriot</option> <option value="Czech">Czech</option> <option value="Danish">Danish</option> <option value="Djibouti">Djibouti</option> <option value="Dominican">Dominican</option> <option value="Dutch">Dutch</option> <option value="East Timorese">East Timorese</option> <option value="Ecuadorean">Ecuadorean</option> <option value="Egyptian">Egyptian</option> <option value="Emirian">Emirian</option> <option value="Equatorial Guinean">Equatorial Guinean</option> <option value="Eritrean">Eritrean</option> <option value="Estonian">Estonian</option> <option value="Ethiopian">Ethiopian</option> <option value="Fijian">Fijian</option> <option value="Filipino">Filipino</option> <option value="Finnish">Finnish</option> <option value="French">French</option> <option value="Gabonese">Gabonese</option> <option value="Gambian">Gambian</option> <option value="Georgian">Georgian</option> <option value="German">German</option> <option value="Ghanaian">Ghanaian</option> <option value="Greek">Greek</option> <option value="Grenadian">Grenadian</option> <option value="Guatemalan">Guatemalan</option> <option value="Guinea-Bissauan">Guinea-Bissauan</option> <option value="Guinean">Guinean</option> <option value="Guyanese">Guyanese</option> <option value="Haitian">Haitian</option> <option value="Herzegovinian">Herzegovinian</option> <option value="Honduran">Honduran</option> <option value="Hungarian">Hungarian</option> <option value="Icelander">Icelander</option> <option value="Indian">Indian</option> <option value="Indonesian">Indonesian</option> <option value="Iranian">Iranian</option> <option value="Iraqi">Iraqi</option> <option value="Irish">Irish</option> <option value="Israeli">Israeli</option> <option value="Italian">Italian</option> <option value="Ivorian">Ivorian</option> <option value="Jamaican">Jamaican</option> <option value="Japanese">Japanese</option> <option value="Jordanian">Jordanian</option> <option value="Kazakhstani">Kazakhstani</option> <option value="Kenyan">Kenyan</option> <option value="Kittian and Nevisian">Kittian and Nevisian</option> <option value="Kuwaiti">Kuwaiti</option> <option value="Kyrgyz">Kyrgyz</option> <option value="Laotian">Laotian</option> <option value="Latvian">Latvian</option> <option value="Lebanese">Lebanese</option> <option value="Liberian">Liberian</option> <option value="Libyan">Libyan</option> <option value="Liechtensteiner">Liechtensteiner</option> <option value="Lithuanian">Lithuanian</option> <option value="Luxembourger">Luxembourger</option> <option value="Macedonian">Macedonian</option> <option value="Malagasy">Malagasy</option> <option value="Malawian">Malawian</option> <option value="Malaysian">Malaysian</option> <option value="Maldivan">Maldivan</option> <option value="Malian">Malian</option> <option value="Maltese">Maltese</option> <option value="Marshallese">Marshallese</option> <option value="Mauritanian">Mauritanian</option> <option value="Mauritian">Mauritian</option> <option value="Mexican">Mexican</option> <option value="Micronesian">Micronesian</option> <option value="Moldovan">Moldovan</option> <option value="Monacan">Monacan</option> <option value="Mongolian">Mongolian</option> <option value="Moroccan">Moroccan</option> <option value="Mosotho">Mosotho</option> <option value="Motswana">Motswana</option> <option value="Mozambican">Mozambican</option> <option value="Namibian">Namibian</option> <option value="Nauruan">Nauruan</option> <option value="Nepalese">Nepalese</option> <option value="Netherlander">Netherlander</option> <option value="New Zealander">New Zealander</option> <option value="Ni-Vanuatu">Ni-Vanuatu</option> <option value="Nicaraguan">Nicaraguan</option> <option value="Nigerian">Nigerian</option> <option value="Nigerien">Nigerien</option> <option value="North Korean">North Korean</option> <option value="Northern Irish">Northern Irish</option> <option value="Norwegian">Norwegian</option> <option value="Omani">Omani</option> <option value="Pakistani">Pakistani</option> <option value="Palauan">Palauan</option> <option value="Panamanian">Panamanian</option> <option value="Papua new Guinean">Papua new Guinean</option> <option value="Paraguayan">Paraguayan</option> <option value="Peruvian">Peruvian</option> <option value="Polish">Polish</option> <option value="Portuguese">Portuguese</option> <option value="Qatari">Qatari</option> <option value="Romanian">Romanian</option> <option value="Russian">Russian</option> <option value="Rwandan">Rwandan</option> <option value="Saint Lucian">Saint Lucian</option> <option value="Salvadoran">Salvadoran</option> <option value="Samoan">Samoan</option> <option value="San Marinese">San Marinese</option> <option value="Sao Tomean">Sao Tomean</option> <option value="Saudi">Saudi</option> <option value="Scottish">Scottish</option> <option value="Senegalese">Senegalese</option> <option value="Serbian">Serbian</option> <option value="Seychellois">Seychellois</option> <option value="Sierra Leonean">Sierra Leonean</option> <option value="Singaporean">Singaporean</option> <option value="Slovakian">Slovakian</option> <option value="Slovenian">Slovenian</option> <option value="Solomon Islander">Solomon Islander</option> <option value="Somali">Somali</option> <option value="South African">South African</option> <option value="South Korean">South Korean</option> <option value="Spanish">Spanish</option> <option value="Sri Lankan">Sri Lankan</option> <option value="Sudanese">Sudanese</option> <option value="Surinamer">Surinamer</option> <option value="Swazi">Swazi</option> <option value="Swedish">Swedish</option> <option value="Swiss">Swiss</option> <option value="Syrian">Syrian</option> <option value="Taiwanese">Taiwanese</option> <option value="Tajik">Tajik</option> <option value="Tanzanian">Tanzanian</option> <option value="Thai">Thai</option> <option value="Togolese">Togolese</option> <option value="Tongan">Tongan</option> <option value="Trinidadian Tobagonian">Trinidadian Tobagonian</option> <option value="Tunisian">Tunisian</option> <option value="Turkish">Turkish</option> <option value="Tuvaluan">Tuvaluan</option> <option value="Ugandan">Ugandan</option> <option value="Ukrainian">Ukrainian</option> <option value="Uruguayan">Uruguayan</option> <option value="Uzbekistani">Uzbekistani</option> <option value="Venezuelan">Venezuelan</option> <option value="Vietnamese">Vietnamese</option> <option value="Welsh">Welsh</option> <option value="Yemenite">Yemenite</option> <option value="Zambian">Zambian</option> <option value="Zimbabwean">Zimbabwean</option></select>
        </div>

        <div class="form-group">
            <label for="enquiry_pax">Total Number of Travellers*</label><br>
            <select name="enquiry[pax]" id="enquiry_pax" class="form-control"><option value="">Select</option><option value="1">1</option><option value="2">2</option><option value="3">3</option><option value="4">4</option><option value="5">5</option><option value="6">6</option><option value="7">7</option><option value="8">8</option><option value="9">9</option><option value="10">10</option><option value="11">11</option><option value="12">12</option><option value="13">13</option><option value="14">14</option><option value="15">15</option><option value="16">16</option><option value="17">17</option><option value="18">18</option><option value="19">19</option><option value="20">20</option></select>
        </div>

        <div class="form-group">
            <label for="enquiry_cruise_id">Cruise Type*</label><br>
            <select class="form-control" id="enquiry_cruise_id" name="enquiry[cruise_id]">
                <option value="">Please Select</option>
            </select>
        </div>
        <div class="form-group">
            <label for="enquiry_direction_id">Direction*</label><br>
            <select class="form-control" id="enquiry_direction_id" name="enquiry[direction_id]">
                <option value="">None</option>
            </select>
        </div>

        <div class="form-group">
            <label for="enquiry_tour_id">Departure Date*</label><br>
            <select class="form-control" id="enquiry_tour_id" name="enquiry[tour_id]">
                <option value="">None</option>
            </select>
        </div>

        <div class="form-group">
            <label for="enquiry_ship_id">Ship*</label><br>
            <select class="form-control"  id="enquiry_ship_id" name="enquiry[ship]">
                <option value="">None</option>
            </select>
        </div>

        <div class="form-group">
            <label for="note">Additional Information</label><br>
            <textarea id="note" name="enquiry[note]" class="form-control" rows="3" maxlength="250" placeholder="Max 250 Characters"></textarea>
        </div>
         <button class="btn btn-info" type="submit">Submit</button>
        </div>
    </div>
</form>

## Versions

This is beta version

<script async src="//jsfiddle.net/190m8vd9/embed/"></script>

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
