
![logo](./Assets/logo.png)


# :earth_africa: CountryData.Net
[![Gitter](https://badges.gitter.im/CountryDataDotnet/community.svg)](https://gitter.im/CountryDataDotnet/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)   
A simple cross-platform offline .NET library for getting Global Country Data without making any HTTP calls.


| | |
|-|-|
| nuget downloads | [![](https://img.shields.io/nuget/dt/CountryData.Standard)](https://www.nuget.org/packages/CountryData.Standard) |
| builds | ![.NET](https://github.com/frankodoom/CountryData.Standard/actions/workflows/dotnet.yml/badge.svg?branch=master) |
|code coverage|[![codecov](https://codecov.io/github/frankodoom/CountryData.Net/graph/badge.svg?token=E79CY267AR)](https://codecov.io/github/frankodoom/CountryData.Net)



### Features

- 📄 Load country data from a JSON file
- 🌍 Get all country data
- 🏳️‍🌈 Get a single country's data by its short code
- 🚩 Get a country's emoji flag by its short code
- 🗺️ Get regions of a country by its short code
- 🌎 Get a list of all country names
- ☎️ Get a country's phone code by its short code
- 🌐 Get a country's data by its phone code

### Install Library
##### Package Manager
```cSharp
   PM> Install-Package CountryData.Standard -Version 1.3.0
```

##### .NET CLI
```cSharp
   > dotnet add package CountryData.Standard --version 1.3.0
```


### Usage

This production-grade package can be used with .NET Core Webapi, .NET console applications, .NET Maui, Xamarin, Blazor, and mobile apps. It is compatible with both .NET Core and .NET Framework projects.

For detailed instructions on how to use the library, please refer to our [documentation](./doc/README.md).

For a quick start, you can check out the  `Simple code` folder   provided in the repository.




### Initialize the Country data object

```cSharp
       //loads all Country Data via the constructor (You can initialize this once as a singleton)
       var helper = new CountryHelper();
```


### Get list of Countries 
```cSharp
       var countries = helper.GetCountries();
       foreach (var country in countries) 
         Console.WriteLine(country);
```


### Get list of Regions in a Country by Country Code
```cSharp
       var regions = helper.GetRegionByCountryCode("GH");
       foreach (var region in regions)
         Console.WriteLine(region.Name);
```
### Using lambda for custom querries
#### `GetCountryData()` returns an `IEnumerable<Country>` which can be querried with Lambda for a more flexible usage.
```cSharp
      //example1
      var data = helper.GetCountryData();
       //get list of countries by their Names
      var countries = data.Select(c => c.CountryName).ToList();
       foreach (var country in countries)
         Console.WriteLine(country);
       
       
       //example 2
       data.Where(x => x.CountryShortCode == "US")
                              .Select(r=>r.Regions).FirstOrDefault()
                              .ToList();
```


####  List of supported ISO-3166-1 country codes, their codepoint pairs and Emoji Flags.

|ISO|Emoji|Unicode|Name|PhoneCode 
|--- |--- |--- |--- |------|
|AD|🇦🇩|U+1F1E6 U+1F1E9|Andorra|
|AE|🇦🇪|U+1F1E6 U+1F1EA|United Arab Emirates|
|AF|🇦🇫|U+1F1E6 U+1F1EB|Afghanistan|
|AG|🇦🇬|U+1F1E6 U+1F1EC|Antigua and Barbuda|
|AI|🇦🇮|U+1F1E6 U+1F1EE|Anguilla|
|AL|🇦🇱|U+1F1E6 U+1F1F1|Albania|
|AM|🇦🇲|U+1F1E6 U+1F1F2|Armenia|
|AO|🇦🇴|U+1F1E6 U+1F1F4|Angola|
|AQ|🇦🇶|U+1F1E6 U+1F1F6|Antarctica|
|AR|🇦🇷|U+1F1E6 U+1F1F7|Argentina|
|AS|🇦🇸|U+1F1E6 U+1F1F8|American Samoa|
|AT|🇦🇹|U+1F1E6 U+1F1F9|Austria|
|AU|🇦🇺|U+1F1E6 U+1F1FA|Australia|
|AW|🇦🇼|U+1F1E6 U+1F1FC|Aruba|
|AX|🇦🇽|U+1F1E6 U+1F1FD|Åland Islands|
|AZ|🇦🇿|U+1F1E6 U+1F1FF|Azerbaijan|
|BA|🇧🇦|U+1F1E7 U+1F1E6|Bosnia and Herzegovina|
|BB|🇧🇧|U+1F1E7 U+1F1E7|Barbados|
|BD|🇧🇩|U+1F1E7 U+1F1E9|Bangladesh|
|BE|🇧🇪|U+1F1E7 U+1F1EA|Belgium|
|BF|🇧🇫|U+1F1E7 U+1F1EB|Burkina Faso|
|BG|🇧🇬|U+1F1E7 U+1F1EC|Bulgaria|
|BH|🇧🇭|U+1F1E7 U+1F1ED|Bahrain|
|BI|🇧🇮|U+1F1E7 U+1F1EE|Burundi|
|BJ|🇧🇯|U+1F1E7 U+1F1EF|Benin|
|BL|🇧🇱|U+1F1E7 U+1F1F1|Saint Barthélemy|
|BM|🇧🇲|U+1F1E7 U+1F1F2|Bermuda|
|BN|🇧🇳|U+1F1E7 U+1F1F3|Brunei Darussalam|
|BO|🇧🇴|U+1F1E7 U+1F1F4|Bolivia|
|BQ|🇧🇶|U+1F1E7 U+1F1F6|Bonaire, Sint Eustatius and Saba|
|BR|🇧🇷|U+1F1E7 U+1F1F7|Brazil|
|BS|🇧🇸|U+1F1E7 U+1F1F8|Bahamas|
|BT|🇧🇹|U+1F1E7 U+1F1F9|Bhutan|
|BV|🇧🇻|U+1F1E7 U+1F1FB|Bouvet Island|
|BW|🇧🇼|U+1F1E7 U+1F1FC|Botswana|
|BY|🇧🇾|U+1F1E7 U+1F1FE|Belarus|
|BZ|🇧🇿|U+1F1E7 U+1F1FF|Belize|
|CA|🇨🇦|U+1F1E8 U+1F1E6|Canada|
|CC|🇨🇨|U+1F1E8 U+1F1E8|Cocos (Keeling) Islands|
|CD|🇨🇩|U+1F1E8 U+1F1E9|Congo|
|CF|🇨🇫|U+1F1E8 U+1F1EB|Central African Republic|
|CG|🇨🇬|U+1F1E8 U+1F1EC|Congo|
|CH|🇨🇭|U+1F1E8 U+1F1ED|Switzerland|
|CI|🇨🇮|U+1F1E8 U+1F1EE|Côte D'Ivoire|
|CK|🇨🇰|U+1F1E8 U+1F1F0|Cook Islands|
|CL|🇨🇱|U+1F1E8 U+1F1F1|Chile|
|CM|🇨🇲|U+1F1E8 U+1F1F2|Cameroon|
|CN|🇨🇳|U+1F1E8 U+1F1F3|China|
|CO|🇨🇴|U+1F1E8 U+1F1F4|Colombia|
|CR|🇨🇷|U+1F1E8 U+1F1F7|Costa Rica|
|CU|🇨🇺|U+1F1E8 U+1F1FA|Cuba|
|CV|🇨🇻|U+1F1E8 U+1F1FB|Cape Verde|
|CW|🇨🇼|U+1F1E8 U+1F1FC|Curaçao|
|CX|🇨🇽|U+1F1E8 U+1F1FD|Christmas Island|
|CY|🇨🇾|U+1F1E8 U+1F1FE|Cyprus|
|CZ|🇨🇿|U+1F1E8 U+1F1FF|Czech Republic|
|DE|🇩🇪|U+1F1E9 U+1F1EA|Germany|
|DJ|🇩🇯|U+1F1E9 U+1F1EF|Djibouti|
|DK|🇩🇰|U+1F1E9 U+1F1F0|Denmark|
|DM|🇩🇲|U+1F1E9 U+1F1F2|Dominica|
|DO|🇩🇴|U+1F1E9 U+1F1F4|Dominican Republic|
|DZ|🇩🇿|U+1F1E9 U+1F1FF|Algeria|
|EC|🇪🇨|U+1F1EA U+1F1E8|Ecuador|
|EE|🇪🇪|U+1F1EA U+1F1EA|Estonia|
|EG|🇪🇬|U+1F1EA U+1F1EC|Egypt|
|EH|🇪🇭|U+1F1EA U+1F1ED|Western Sahara|
|ER|🇪🇷|U+1F1EA U+1F1F7|Eritrea|
|ES|🇪🇸|U+1F1EA U+1F1F8|Spain|
|ET|🇪🇹|U+1F1EA U+1F1F9|Ethiopia|
|FI|🇫🇮|U+1F1EB U+1F1EE|Finland|
|FJ|🇫🇯|U+1F1EB U+1F1EF|Fiji|
|FK|🇫🇰|U+1F1EB U+1F1F0|Falkland Islands (Malvinas)|
|FM|🇫🇲|U+1F1EB U+1F1F2|Micronesia|
|FO|🇫🇴|U+1F1EB U+1F1F4|Faroe Islands|
|FR|🇫🇷|U+1F1EB U+1F1F7|France|
|GA|🇬🇦|U+1F1EC U+1F1E6|Gabon|
|GB|🇬🇧|U+1F1EC U+1F1E7|United Kingdom|
|GD|🇬🇩|U+1F1EC U+1F1E9|Grenada|
|GE|🇬🇪|U+1F1EC U+1F1EA|Georgia|
|GF|🇬🇫|U+1F1EC U+1F1EB|French Guiana|
|GG|🇬🇬|U+1F1EC U+1F1EC|Guernsey|
|GH|🇬🇭|U+1F1EC U+1F1ED|Ghana|
|GI|🇬🇮|U+1F1EC U+1F1EE|Gibraltar|
|GL|🇬🇱|U+1F1EC U+1F1F1|Greenland|
|GM|🇬🇲|U+1F1EC U+1F1F2|Gambia|
|GN|🇬🇳|U+1F1EC U+1F1F3|Guinea|
|GP|🇬🇵|U+1F1EC U+1F1F5|Guadeloupe|
|GQ|🇬🇶|U+1F1EC U+1F1F6|Equatorial Guinea|
|GR|🇬🇷|U+1F1EC U+1F1F7|Greece|
|GS|🇬🇸|U+1F1EC U+1F1F8|South Georgia|
|GT|🇬🇹|U+1F1EC U+1F1F9|Guatemala|
|GU|🇬🇺|U+1F1EC U+1F1FA|Guam|
|GW|🇬🇼|U+1F1EC U+1F1FC|Guinea-Bissau|
|GY|🇬🇾|U+1F1EC U+1F1FE|Guyana|
|HK|🇭🇰|U+1F1ED U+1F1F0|Hong Kong|
|HM|🇭🇲|U+1F1ED U+1F1F2|Heard Island and Mcdonald Islands|
|HN|🇭🇳|U+1F1ED U+1F1F3|Honduras|
|HR|🇭🇷|U+1F1ED U+1F1F7|Croatia|
|HT|🇭🇹|U+1F1ED U+1F1F9|Haiti|
|HU|🇭🇺|U+1F1ED U+1F1FA|Hungary|
|ID|🇮🇩|U+1F1EE U+1F1E9|Indonesia|
|IE|🇮🇪|U+1F1EE U+1F1EA|Ireland|
|IL|🇮🇱|U+1F1EE U+1F1F1|Israel|
|IM|🇮🇲|U+1F1EE U+1F1F2|Isle of Man|
|IN|🇮🇳|U+1F1EE U+1F1F3|India|
|IO|🇮🇴|U+1F1EE U+1F1F4|British Indian Ocean Territory|
|IQ|🇮🇶|U+1F1EE U+1F1F6|Iraq|
|IR|🇮🇷|U+1F1EE U+1F1F7|Iran|
|IS|🇮🇸|U+1F1EE U+1F1F8|Iceland|
|IT|🇮🇹|U+1F1EE U+1F1F9|Italy|
|JE|🇯🇪|U+1F1EF U+1F1EA|Jersey|
|JM|🇯🇲|U+1F1EF U+1F1F2|Jamaica|
|JO|🇯🇴|U+1F1EF U+1F1F4|Jordan|
|JP|🇯🇵|U+1F1EF U+1F1F5|Japan|
|KE|🇰🇪|U+1F1F0 U+1F1EA|Kenya|
|KG|🇰🇬|U+1F1F0 U+1F1EC|Kyrgyzstan|
|KH|🇰🇭|U+1F1F0 U+1F1ED|Cambodia|
|KI|🇰🇮|U+1F1F0 U+1F1EE|Kiribati|
|KM|🇰🇲|U+1F1F0 U+1F1F2|Comoros|
|KN|🇰🇳|U+1F1F0 U+1F1F3|Saint Kitts and Nevis|
|KP|🇰🇵|U+1F1F0 U+1F1F5|North Korea|
|KR|🇰🇷|U+1F1F0 U+1F1F7|South Korea|
|KW|🇰🇼|U+1F1F0 U+1F1FC|Kuwait|
|KY|🇰🇾|U+1F1F0 U+1F1FE|Cayman Islands|
|KZ|🇰🇿|U+1F1F0 U+1F1FF|Kazakhstan|
|LA|🇱🇦|U+1F1F1 U+1F1E6|Lao People's Democratic Republic|
|LB|🇱🇧|U+1F1F1 U+1F1E7|Lebanon|
|LC|🇱🇨|U+1F1F1 U+1F1E8|Saint Lucia|
|LI|🇱🇮|U+1F1F1 U+1F1EE|Liechtenstein|
|LK|🇱🇰|U+1F1F1 U+1F1F0|Sri Lanka|
|LR|🇱🇷|U+1F1F1 U+1F1F7|Liberia|
|LS|🇱🇸|U+1F1F1 U+1F1F8|Lesotho|
|LT|🇱🇹|U+1F1F1 U+1F1F9|Lithuania|
|LU|🇱🇺|U+1F1F1 U+1F1FA|Luxembourg|
|LV|🇱🇻|U+1F1F1 U+1F1FB|Latvia|
|LY|🇱🇾|U+1F1F1 U+1F1FE|Libya|
|MA|🇲🇦|U+1F1F2 U+1F1E6|Morocco|
|MC|🇲🇨|U+1F1F2 U+1F1E8|Monaco|
|MD|🇲🇩|U+1F1F2 U+1F1E9|Moldova|
|ME|🇲🇪|U+1F1F2 U+1F1EA|Montenegro|
|MF|🇲🇫|U+1F1F2 U+1F1EB|Saint Martin (French Part)|
|MG|🇲🇬|U+1F1F2 U+1F1EC|Madagascar|
|MH|🇲🇭|U+1F1F2 U+1F1ED|Marshall Islands|
|MK|🇲🇰|U+1F1F2 U+1F1F0|Macedonia|
|ML|🇲🇱|U+1F1F2 U+1F1F1|Mali|
|MM|🇲🇲|U+1F1F2 U+1F1F2|Myanmar|
|MN|🇲🇳|U+1F1F2 U+1F1F3|Mongolia|
|MO|🇲🇴|U+1F1F2 U+1F1F4|Macao|
|MP|🇲🇵|U+1F1F2 U+1F1F5|Northern Mariana Islands|
|MQ|🇲🇶|U+1F1F2 U+1F1F6|Martinique|
|MR|🇲🇷|U+1F1F2 U+1F1F7|Mauritania|
|MS|🇲🇸|U+1F1F2 U+1F1F8|Montserrat|
|MT|🇲🇹|U+1F1F2 U+1F1F9|Malta|
|MU|🇲🇺|U+1F1F2 U+1F1FA|Mauritius|
|MV|🇲🇻|U+1F1F2 U+1F1FB|Maldives|
|MW|🇲🇼|U+1F1F2 U+1F1FC|Malawi|
|MX|🇲🇽|U+1F1F2 U+1F1FD|Mexico|
|MY|🇲🇾|U+1F1F2 U+1F1FE|Malaysia|
|MZ|🇲🇿|U+1F1F2 U+1F1FF|Mozambique|
|NA|🇳🇦|U+1F1F3 U+1F1E6|Namibia|
|NC|🇳🇨|U+1F1F3 U+1F1E8|New Caledonia|
|NE|🇳🇪|U+1F1F3 U+1F1EA|Niger|
|NF|🇳🇫|U+1F1F3 U+1F1EB|Norfolk Island|
|NG|🇳🇬|U+1F1F3 U+1F1EC|Nigeria|
|NI|🇳🇮|U+1F1F3 U+1F1EE|Nicaragua|
|NL|🇳🇱|U+1F1F3 U+1F1F1|Netherlands|
|NO|🇳🇴|U+1F1F3 U+1F1F4|Norway|
|NP|🇳🇵|U+1F1F3 U+1F1F5|Nepal|
|NR|🇳🇷|U+1F1F3 U+1F1F7|Nauru|
|NU|🇳🇺|U+1F1F3 U+1F1FA|Niue|
|NZ|🇳🇿|U+1F1F3 U+1F1FF|New Zealand|
|OM|🇴🇲|U+1F1F4 U+1F1F2|Oman|
|PA|🇵🇦|U+1F1F5 U+1F1E6|Panama|
|PE|🇵🇪|U+1F1F5 U+1F1EA|Peru|
|PF|🇵🇫|U+1F1F5 U+1F1EB|French Polynesia|
|PG|🇵🇬|U+1F1F5 U+1F1EC|Papua New Guinea|
|PH|🇵🇭|U+1F1F5 U+1F1ED|Philippines|
|PK|🇵🇰|U+1F1F5 U+1F1F0|Pakistan|
|PL|🇵🇱|U+1F1F5 U+1F1F1|Poland|
|PM|🇵🇲|U+1F1F5 U+1F1F2|Saint Pierre and Miquelon|
|PN|🇵🇳|U+1F1F5 U+1F1F3|Pitcairn|
|PR|🇵🇷|U+1F1F5 U+1F1F7|Puerto Rico|
|PS|🇵🇸|U+1F1F5 U+1F1F8|Palestinian Territory|
|PT|🇵🇹|U+1F1F5 U+1F1F9|Portugal|
|PW|🇵🇼|U+1F1F5 U+1F1FC|Palau|
|PY|🇵🇾|U+1F1F5 U+1F1FE|Paraguay|
|QA|🇶🇦|U+1F1F6 U+1F1E6|Qatar|
|RE|🇷🇪|U+1F1F7 U+1F1EA|Réunion|
|RO|🇷🇴|U+1F1F7 U+1F1F4|Romania|
|RS|🇷🇸|U+1F1F7 U+1F1F8|Serbia|
|RU|🇷🇺|U+1F1F7 U+1F1FA|Russia|
|RW|🇷🇼|U+1F1F7 U+1F1FC|Rwanda|
|SA|🇸🇦|U+1F1F8 U+1F1E6|Saudi Arabia|
|SB|🇸🇧|U+1F1F8 U+1F1E7|Solomon Islands|
|SC|🇸🇨|U+1F1F8 U+1F1E8|Seychelles|
|SD|🇸🇩|U+1F1F8 U+1F1E9|Sudan|
|SE|🇸🇪|U+1F1F8 U+1F1EA|Sweden|
|SG|🇸🇬|U+1F1F8 U+1F1EC|Singapore|
|SH|🇸🇭|U+1F1F8 U+1F1ED|Saint Helena, Ascension and Tristan Da Cunha|
|SI|🇸🇮|U+1F1F8 U+1F1EE|Slovenia|
|SJ|🇸🇯|U+1F1F8 U+1F1EF|Svalbard and Jan Mayen|
|SK|🇸🇰|U+1F1F8 U+1F1F0|Slovakia|
|SL|🇸🇱|U+1F1F8 U+1F1F1|Sierra Leone|
|SM|🇸🇲|U+1F1F8 U+1F1F2|San Marino|
|SN|🇸🇳|U+1F1F8 U+1F1F3|Senegal|
|SO|🇸🇴|U+1F1F8 U+1F1F4|Somalia|
|SR|🇸🇷|U+1F1F8 U+1F1F7|Suriname|
|SS|🇸🇸|U+1F1F8 U+1F1F8|South Sudan|
|ST|🇸🇹|U+1F1F8 U+1F1F9|Sao Tome and Principe|
|SV|🇸🇻|U+1F1F8 U+1F1FB|El Salvador|
|SX|🇸🇽|U+1F1F8 U+1F1FD|Sint Maarten (Dutch Part)|
|SY|🇸🇾|U+1F1F8 U+1F1FE|Syrian Arab Republic|
|SZ|🇸🇿|U+1F1F8 U+1F1FF|Swaziland|
|TC|🇹🇨|U+1F1F9 U+1F1E8|Turks and Caicos Islands|
|TD|🇹🇩|U+1F1F9 U+1F1E9|Chad|
|TF|🇹🇫|U+1F1F9 U+1F1EB|French Southern Territories|
|TG|🇹🇬|U+1F1F9 U+1F1EC|Togo|
|TH|🇹🇭|U+1F1F9 U+1F1ED|Thailand|
|TJ|🇹🇯|U+1F1F9 U+1F1EF|Tajikistan|
|TK|🇹🇰|U+1F1F9 U+1F1F0|Tokelau|
|TL|🇹🇱|U+1F1F9 U+1F1F1|Timor-Leste|
|TM|🇹🇲|U+1F1F9 U+1F1F2|Turkmenistan|
|TN|🇹🇳|U+1F1F9 U+1F1F3|Tunisia|
|TO|🇹🇴|U+1F1F9 U+1F1F4|Tonga|
|TR|🇹🇷|U+1F1F9 U+1F1F7|Turkey|
|TT|🇹🇹|U+1F1F9 U+1F1F9|Trinidad and Tobago|
|TV|🇹🇻|U+1F1F9 U+1F1FB|Tuvalu|
|TW|🇹🇼|U+1F1F9 U+1F1FC|Taiwan|
|TZ|🇹🇿|U+1F1F9 U+1F1FF|Tanzania|
|UA|🇺🇦|U+1F1FA U+1F1E6|Ukraine|
|UG|🇺🇬|U+1F1FA U+1F1EC|Uganda|
|UM|🇺🇲|U+1F1FA U+1F1F2|United States Minor Outlying Islands|
|US|🇺🇸|U+1F1FA U+1F1F8|United States|
|UY|🇺🇾|U+1F1FA U+1F1FE|Uruguay|
|UZ|🇺🇿|U+1F1FA U+1F1FF|Uzbekistan|
|VA|🇻🇦|U+1F1FB U+1F1E6|Vatican City|
|VC|🇻🇨|U+1F1FB U+1F1E8|Saint Vincent and The Grenadines|
|VE|🇻🇪|U+1F1FB U+1F1EA|Venezuela|
|VG|🇻🇬|U+1F1FB U+1F1EC|Virgin Islands, British|
|VI|🇻🇮|U+1F1FB U+1F1EE|Virgin Islands, U.S.|
|VN|🇻🇳|U+1F1FB U+1F1F3|Viet Nam|
|VU|🇻🇺|U+1F1FB U+1F1FA|Vanuatu|
|WF|🇼🇫|U+1F1FC U+1F1EB|Wallis and Futuna|
|WS|🇼🇸|U+1F1FC U+1F1F8|Samoa|
|YE|🇾🇪|U+1F1FE U+1F1EA|Yemen|
|YT|🇾🇹|U+1F1FE U+1F1F9|Mayotte|
|ZA|🇿🇦|U+1F1FF U+1F1E6|South Africa|
|ZM|🇿🇲|U+1F1FF U+1F1F2|Zambia|
|ZW|🇿🇼|U+1F1FF U+1F1FC|Zimbabwe|



## Contributing

Contributions are welcome! Please see our [Contributing Guide](CONTRIBUTING.md) for more details.Creating a `Code of Conduct` for your project involves defining the standards of behavior expected from contributors and maintainers. This document helps ensure that the community around your project is welcoming and collaborative. Here's a basic template you can use and customize for your project:


### Comming Soon
* Support for more ISO Standard Country Data
* Support for ISO 3166 Country A3 Codes
* Country ShortCode Enums



## License

This project is licensed under the terms of the [LICENSE](LICENSE).
