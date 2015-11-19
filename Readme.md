# faker.js - generate massive amounts of fake data in the browser and node.js

![faker.js](http://imgur.com/KiinQ.png)

[![Build Status](https://travis-ci.org/Marak/faker.js.svg?branch=master)](https://travis-ci.org/Marak/Faker.js)

## Demo

[Demo Site](http://marak.com/faker.js/">http://marak.com/faker.js/)

## USAGE

### browser

	<script src = "faker.js" type = "text/javascript"></script>
    <script>
    	var randomName = faker.name.findName(); 		// => OUTPUTS: Caitlyn Kerluke
        var randomEmail = faker.internet.email(); 		// => OUTPUTS: Rusty@arne.info
        var randomCard = faker.helpers.createCard(); 	// => OUTPUTS: An Object containing many properties
    </script>

### node.js

	var faker = require('./faker');

    var randomName = faker.name.findName(); 			// => OUTPUTS: Rowan Nikolaus
    var randomEmail = faker.internet.email(); 			// => OUTPUTS: Kassandra.Haley@erich.biz
    var randomCard = faker.helpers.createCard(); 		// => OUTPUTS: An object containing many properties

### Localization

As of version `v2.0.0` faker.js supports 27 different language definition packs.

The default language is set to English.

Setting a new locale is simple:

	// sets locale to de
	faker.locale = "de";

Read further for complete list of locales.

## API

## faker.name

Functions to generate random names for people

	faker.name.firstName(); 					// => OUTPUTS: Rowan

	faker.name.lastName(); 						// => OUTPUTS: Kerluke

	faker.name.findName(); 						// => OUTPUTS: Rowan Kerluke

	faker.name.findName("John"); 				// => OUTPUTS: John Rippin
	faker.name.findName("John", "Walsh"); 		// => OUTPUTS: John Walsh
	faker.name.findName("John", "Walsh"); 		// => OUTPUTS: Mr. John Walsh
	faker.name.findName("John", "Walsh"); 		// => OUTPUTS: John Walsh Sr.

	faker.name.prefix(); 						// => OUTPUTS: Mr.

	faker.name.suffix(); 						// => OUTPUTS: Jr.

## faker.address

Functions to generate random address information

	faker.address.zipCode(); 					// => OUTPUTS: 60184-487

	faker.address.city(); 						// => OUTPUTS: North Bellshire

	faker.address.cityPrefix(); 				// => OUTPUTS: South

	faker.address.citySuffix(); 				// => OUTPUTS: town

	faker.address.streetName(); 				// =>  OUTPUTS: Ferry Alley

	faker.address.streetAddress(); 				// =>  OUTPUTS: 74589 Kertzmann Mall
	faker.address.streetAddress(true); 			// =>  OUTPUTS: 51154 DuBuque Extensions Suite 261

	faker.address.streetSuffix(); 				// =>  OUTPUTS: Canyon

	faker.address.secondaryAddress(); 			// =>  OUTPUTS: Apt. 123

	faker.address.county(); 					// =>  OUTPUTS: Bedfordshire

	faker.address.country(); 					// =>  OUTPUTS: Austria

	faker.address.state(); 						// =>  OUTPUTS: Kansas

	faker.address.stateAbbr(); 					// =>  OUTPUTS: KS

	faker.address.latitude(); 					// =>  OUTPUTS: 52.9541

	faker.address.longitude(); 					// =>  OUTPUTS: -1.1640

## faker.phone

Functions to generate phone numbers

	faker.phone.phoneNumber();					// => OUTPUTS: 123-456-7890
	faker.phone.phoneNumber('##### ######);		// => OUTPUTS: 12345 678901

	faker.phone.phoneNumberFormat();			// => OUTPUTS: 123-456-7890
	faker.phone.phoneNumberFormat(1);			// => OUTPUTS: (123) 456-7890

	faker.phone.phoneFormats();					// => OUTPUTS: ###-###-####

## faker.internet

Functions to generate common internet information, such as email addresses or domains

	faker.internet.avatar();								// => OUTPUTS: https://s3.amazonaws.com/uifaces/faces/twitter/jarjan/128.jpg

	faker.internet.email();									// => OUTPUTS: rowan.haley@gmail.com
	faker.internet.email('james');							// => OUTPUTS: james.green@hotmail.com
	faker.internet.email('james', 'bond');					// => OUTPUTS: james.bond53@yahoo.com
	faker.internet.email('james', 'bond', 'a.com');			// => OUTPUTS: james_bond@a.com

	faker.internet.userName();								// => OUTPUTS: rowan.haley
	faker.internet.userName('james');						// => OUTPUTS: james_green6
	faker.internet.userName('james', 'bond');				// => OUTPUTS: james41
	faker.internet.userName('james', 'bond');				// => OUTPUTS: james.bond

	faker.internet.domainName();							// => OUTPUTS: joe.com

	faker.internet.domainSuffix();							// => OUTPUTS: info

	faker.internet.domainWord();							// => OUTPUTS: aurelio

	faker.internet.ip();									// => OUTPUTS: 192.154.21.265

	faker.internet.userAgent();								// => OUTPUTS: Mozilla/5.0 (Windows; U; Windows NT 5.3) AppleWebKit/1.5 (KHTML, like Gecko) Chrome

	faker.internet.color();									// => OUTPUTS: #

	faker.internet.password();								// => OUTPUTS: Sg05EU9qJ866K_V
    faker.internet.password(25);							// => OUTPUTS: bck57QGpCk6NZLn6Jpb0OEw4F
    faker.internet.password(25, true);						// => OUTPUTS: bujolufayihohuduqucipeweq
	faker.internet.password(25, false, /\d/);				// => OUTPUTS: 8616909730935728756345227
	faker.internet.password(25, true, /\w/, 'password'); 	// => OUTPUTS: passwordabaweyolayaqogote

## faker.company

Functions to generate Company Information

	faker.company.suffixes();							// => OUTPUTS: ["Inc", "and Sons", "LLC", "Group", "and Daughters"]

	faker.company.companyName();						// => OUTPUTS: Block and Sons
	faker.company.companyName(1);						// => OUTPUTS: Block-Paucek
	faker.company.companyName(2);						// => OUTPUTS: Block, Paucek and Kub

	faker.company.companySuffix();						// => OUTPUTS: Group

	faker.company.catchPhrase();						// => OUTPUTS: Devolved bifurcated attitude

	faker.company.bs();									// => OUTPUTS: interactive enhance solutions

	faker.company.catchPhraseAdjective();				// => OUTPUTS: Proactive

	faker.company.catchPhraseDescriptor();				// => OUTPUTS: intangible

	faker.company.catchPhraseNoun();					// => OUTPUTS: definition

	faker.company.bsAdjective();						// => OUTPUTS: best-of-breed

	faker.company.bsBuzz();								// => OUTPUTS: syndicate

	faker.company.bsNoun();								// => OUTPUTS: metrics

## faker.commerce

Functions to generate information normally associated with commerce

	faker.commerce.color();							// => OUTPUTS: yellow

	faker.commerce.department();					// => OUTPUTS: Books, Movies & Games
	faker.commerce.department(1);					// => OUTPUTS: Garden
	faker.commerce.department(3);					// => OUTPUTS: Home & Garden
	faker.commerce.department(3, true);				// => OUTPUTS: Home, Garden & Outdoors

	faker.commerce.productName();					// => OUTPUTS: gorgeous metal bike
	faker.commerce.productName({seed: 1234});		// => ALWAYS OUTPUTS: Intelligent Concrete Mouse

	faker.commerce.price();							// => OUTPUTS: 149.99
	faker.commerce.price(10, 20);					// => OUTPUTS: 15.50
	faker.commerce.price(10, 1000, 2, '£');			// => OUTPUTS: £495.21

## faker.image

Functions to generate random images, images provided by [lorempixel](http://lorempixel.com)

	faker.image.image();							// => OUTPUTS: http://lorempixel.com/640/480/animals

	faker.image.avatar();							// => OUTPUTS: https://s3.amazonaws.com/uifaces/faces/twitter/jarjan/128.jpg

	faker.image.imageUrl();							// => OUTPUTS: http://lorempixel.com/640/480
	faker.image.imageUrl(300);						// => OUTPUTS: http://lorempixel.com/300/480
	faker.image.imageUrl(300, 200);					// => OUTPUTS: http://lorempixel.com/300/200
	faker.image.imageUrl(300, 200, 'business');		// => OUTPUTS: http://lorempixel.com/300/200/business

	faker.image.abstract();							// => OUTPUTS: http://lorempixel.com/640/480/abstract
	faker.image.abstract(300, 200);					// => OUTPUTS: http://lorempixel.com/300/200/abstract

	faker.image.animals();							// => OUTPUTS: http://lorempixel.com/640/480/animals
	faker.image.animals(300, 200);					// => OUTPUTS: http://lorempixel.com/300/200/animals

	faker.image.business();							// => OUTPUTS: http://lorempixel.com/640/480/business
	faker.image.business(300, 200);					// => OUTPUTS: http://lorempixel.com/300/200/business

	faker.image.cats();								// => OUTPUTS: http://lorempixel.com/640/480/cats
	faker.image.cats(300, 200);						// => OUTPUTS: http://lorempixel.com/300/200/cats

	faker.image.city();								// => OUTPUTS: http://lorempixel.com/640/480/city
	faker.image.city(300, 200);						// => OUTPUTS: http://lorempixel.com/300/200/city

	faker.image.food();								// => OUTPUTS: http://lorempixel.com/640/480/food
	faker.image.food(300, 200);						// => OUTPUTS: http://lorempixel.com/300/200/food

	faker.image.nightlife();						// => OUTPUTS: http://lorempixel.com/640/480/nightlife
	faker.image.nightlife(300, 200);				// => OUTPUTS: http://lorempixel.com/300/200/nightlife

	faker.image.fashion();							// => OUTPUTS: http://lorempixel.com/640/480/fashion
	faker.image.fashion(300, 200);					// => OUTPUTS: http://lorempixel.com/300/200/fashion

	faker.image.people();							// => OUTPUTS: http://lorempixel.com/640/480/people
	faker.image.people(300, 200);					// => OUTPUTS: http://lorempixel.com/300/200/people

	faker.image.nature();							// => OUTPUTS: http://lorempixel.com/640/480/nature
	faker.image.nature(300, 200);					// => OUTPUTS: http://lorempixel.com/300/200/nature

	faker.image.sports();							// => OUTPUTS: http://lorempixel.com/640/480/sports
	faker.image.sports(300, 200);					// => OUTPUTS: http://lorempixel.com/300/200/sports

	faker.image.technics();							// => OUTPUTS: http://lorempixel.com/640/480/technics
	faker.image.technics(300, 200);					// => OUTPUTS: http://lorempixel.com/300/200/technics

	faker.image.transport();						// => OUTPUTS: http://lorempixel.com/640/480/transport
	faker.image.transport(300, 200);				// => OUTPUTS: http://lorempixel.com/300/200/transport

## faker.lorem

Functions to provide placeholder text generated by words found in lorem ipsum.

	faker.lorem.words();						// => OUTPUTS: doloremque veritatis sunt
	faker.lorem.words(5);						// => OUTPUTS: dolores neque ipsum amet sed

	faker.lorem.sentence();						// => OUTPUTS: veritatis quia dolores quae adipisci
	faker.lorem.sentence(4, 2);					// => OUTPUTS: dicta quia sequi aperiam voluptatem, consequatur  

	faker.lorem.sentences();					// => OUTPUTS: veniam suscipit consequatur numquam quia \n consectetur voluptate minima \n ducimus dolores similique error id laudantium facilis
	faker.lorem.sentences(2);					// => OUTPUTS: veniam suscipit consequatur numquam quia \n consectetur voluptate minima

	faker.lorem.paragraph();					// => OUTPUTS: veniam suscipit consequatur numquam quia \n consectetur voluptate minima \n ducimus dolores similique error id laudantium facilis \n veritatis quia dolores quae adipisci
	faker.lorem.paragraph(5);					// => OUTPUTS: veniam suscipit consequatur numquam quia \n consectetur voluptate minima \n ducimus dolores similique error id laudantium facilis \n veritatis quia dolores quae adipisci \n doloremque veritatis sunt \n consectetur voluptate minima sequi

	faker.lorem.paragraphs();					// => OUTPUTS: veniam suscipit consequatur numquam quia \n consectetur voluptate minima \n ducimus dolores similique error id laudantium facilis \n veritatis quia dolores quae adipisci \n \r\t veniam suscipit consequatur numquam quia \n consectetur voluptate minima \n ducimus dolores similique error id laudantium facilis \n veritatis quia dolores quae adipisci \n \r\t veniam suscipit consequatur numquam quia \n consectetur voluptate minima \n ducimus dolores similique error id laudantium facilis \n veritatis quia dolores quae

## faker.helpers

Functions to help create data quickly.

	faker.helpers.randomNumber();								// => OUTPUTS: 1
	faker.helpers.randomNumber(10);								// => OUTPUTS: 8
	faker.helpers.randomNumber({min: 5, max: 50});				// => OUTPUTS: 32

	var array = [1, 2];
	faker.helpers.randomize(array);								// => OUTPUTS: 1
	var array = ["item1", "item2", "item3", "item4"];
	faker.helpers.randomize(array);								// => OUTPUTS: item3

	faker.helpers.slugify('test string made of Text');			// => OUTPUTS: test-string-made-of-Text

	faker.helpers.replaceSymbolWithNumber("ext: ####-##");		// => OUTPUTS: ext: 4716-58
	faker.helpers.replaceSymbolWithNumber("$$$.$$", "$");		// => OUTPUTS: 524.26

	faker.helpers.shuffle();									// => OUTPUTS: [ 'a', 'c', 'b' ]
    faker.helpers.shuffle([1, 2, 3, 4]);						// => OUTPUTS: [ 2, 4, 3, 1 ]

	faker.helpers.mustache("test {{key}}", {"key": "string"});	// => OUTPUTS: test string

	faker.helpers.createCard();									// => OUTPUTS: {
																	name: 'Anita Waelchi',
  																	username: 'Terence.Kuhic37',
  																	email: 'Lavern_Kemmer9@hotmail.com',
  																	address: {
																		streetA: 'Gregoria Wells',
																		....
																	}
																}

	faker.helpers.contextualCard();								// => OUTPUTS: {
																	name: 'Annabel',
																	username: 'Annabel_Bauch',
																	avatar: 'https://s3.amazonaws.com/uifaces/faces/twitter/millinet/128.jpg',
																	email: 'Annabel_Bauch.Stoltenberg@gmail.com',
																	dob: Mon Feb 25 1974 03:43:58 GMT+0000 (GMT Standard Time),
																	phone: '(560) 043-3168 x826',
																	address: {
																		street: 'Alfred Lodge',
																		...
																	}
																}

	faker.helpers.userCard(); 									// => OUTPUTS: {
																	name: 'Eugene Rath',
																	username: 'Zelda29',
																	email: 'Adolf95@hotmail.com',
																	address: {
																		street: 'Larson Canyon',
																		suite: 'Suite 156',
																		city: 'Williamsontown',
																		zipcode: '21518-1560',
																		geo: { lat: '-26.6674', lng: '-48.7346' }
																	},
																	phone: '1-242-561-4692 x003',
																	website: 'magnus.org',
																	company: {
																		name: 'Herzog, Stamm and Willms',
																	    catchPhrase: 'Innovative methodical hierarchy',
																	    bs: 'out-of-the-box empower architectures'
																	}
																}

	faker.helpers.createTransaction();							// => OUTPUTS: {
																	amount: '755.59',
																	date: Thu Feb 02 2012 00:00:00 GMT+0000 (GMT Standard Time),
																	business: 'Marks-McLaughlin',
																	name: 'Home Loan Account 9319',
																	type: 'invoice',
																	account: '31060525'
																}

## faker.date

Functions to generate dates

	faker.date.past();									// OUTPUTS: Mon Jan 26 2015 11:19:15 GMT+0000 (GMT Standard Time)
	faker.date.past(3);									// OUTPUTS: Sun Nov 03 2013 01:10:25 GMT+0000 (GMT Standard Time)
	faker.date.past(3, '02/05/2011');					// OUTPUTS: Sun Dec 19 2010 05:59:05 GMT+0000 (GMT Standard Time)

	faker.date.future();								// OUTPUTS: Wed Sep 02 2015 01:25:30 GMT+0100 (GMT Daylight Time)
	faker.date.future(3);								// OUTPUTS: Fri Mar 20 2015 13:47:54 GMT+0000 (GMT Standard Time)
	faker.date.future(3, '02/05/2018');					// OUTPUTS: Sun Jan 27 2019 14:53:44 GMT+0000 (GMT Standard Time)

	faker.date.between('02/05/2011', '02/05/2018');		// OUTPUTS: Thu May 18 2017 04:49:07 GMT+0100 (GMT Daylight Time)

	faker.date.recent();								// OUTPUTS: Wed Mar 11 2015 19:12:05 GMT+0000 (GMT Standard Time)
	faker.date.recent(50);								// OUTPUTS: Wed Jan 28 2015 05:21:22 GMT+0000 (GMT Standard Time)

## faker.random

Functions to provide random information based on passed in items.

	faker.random.number();								// OUTPUTS: 1
	faker.random.number(10);							// OUTPUTS: 8
	faker.random.number({min: 5, max: 50});				// OUTPUTS: 32
	faker.random.number({max: 100, seed: 1234});		// ALWAYS OUTPUTS: 19

	var array = [1, 2];
	faker.random.array_element(array);					// OUTPUTS: 1
	var array = ["item1", "item2", "item3", "item4"];
	faker.random.array_element(array);					// OUTPUTS: item3
	var array = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
	faker.random.array_element(array, {seed: 1234});	// ALWAYS OUTPUTS: 2

	var object = {
		'name': 'john smith',
		'age': 28,
		'value': 1154
	};
	faker.random.object_element(object);				// OUTPUTS: john smith
	faker.random.object_element(object, 'key');			// OUTPUTS: name


## faker.finance

Functions to generate common finance information

	faker.finance.account();						// OUTPUTS: 12451658
	faker.finance.account(5);						// OUTPUTS: 12451

	faker.finance.accountName();					// OUTPUTS: Savings Account

	faker.finance.mask();							// OUTPUTS:

	faker.finance.amount();							// OUTPUTS: 59.54
	faker.finance.amount(900);						// OUTPUTS: 940.15
	faker.finance.amount(900, 2000);				// OUTPUTS: 1889.28
	faker.finance.amount(900, 2000, 2, '$');		// OUTPUTS: $1248.74

	faker.finance.transactionType();				// OUTPUTS: withdrawal

	faker.finance.currencyCode();					// OUTPUTS: AUD

	faker.finance.currencyName();					// OUTPUTS: Australian Dollar

	faker.finance.currencySymbol();					// OUTPUTS: $

## faker.hacker

Functions to generate computer related information

	faker.hacker.abbreviation();					// OUTPUTS: HTTP

	faker.hacker.adjective();						// OUTPUTS: haptic

	faker.hacker.noun();							// OUTPUTS: microchip

	faker.hacker.verb();							// OUTPUTS: compress

	faker.hacker.ingverb();							// OUTPUTS: generating

	faker.hacker.phrase();							// OUTPUTS: We need to calculate the neural EXE interface!

## faker.locale

Gets or Sets the locale. See the "*Supported Locales*" section for a list of allowed values

	faker.locale;							// OUTPUTS: en

	faker.locale = "es"
	faker.locale;							// OUTPUTS: es

## faker.localeFallback

Gets or Sets the locale Fallback, this is used if a value isn't specified in the chosen locale. This defaults to **en**. See the "*Supported Locales*" section for a list of allowed values

	faker.localeFallback;					// OUTPUTS: en

	faker.localeFallback = "en_US"
	faker.localeFallback;					// OUTPUTS: en_US

## Supported Locales

* de
* de_AT
* de_CH
* en
* en_AU
* en_BORK
* en_CA
* en_GB
* en_IND
* en_US
* en_au_ocker
* es
* fa
* fr
* it
* ja
* ko
* nb_NO
* nep
* nl
* pl
* pt_BR
* ru
* sk
* sv
* vi
* zh_CN

## Tests

	npm install .
    make test

You can view a code coverage report generated in `coverage/lcov-report/index.html`.

## Authors

#### Matthew Bergman & Marak Squires

Copyright (c) 2014 Matthew Bergman & Marak Squires http://github.com/marak/faker.js/

faker.js was inspired by and has used data definitions from:

* [https://github.com/stympy/faker/](https://github.com/stympy/faker/) - Copyright (c) 2007-2010 Benjamin Curtis
* [http://search.cpan.org/~jasonk/Data-Faker-0.07/](http://search.cpan.org/~jasonk/Data-Faker-0.07/) - Copyright 2004-2005 by Jason Kohles

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

* The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.
* THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
