<script>
	// @ts-nocheck
	import { browser } from '$app/environment';

	import StepWizard from 'svelte-step-wizard';
	import TickCircle from 'iconsax-svelte/TickCircle.svelte';
	import ArrowRight from 'iconsax-svelte/ArrowRight.svelte';
	import ArrowLeft1 from 'iconsax-svelte/ArrowLeft1.svelte';
	import ArrowRight1 from 'iconsax-svelte/ArrowRight1.svelte';
	import Add from 'iconsax-svelte/Add.svelte';
	import { Tab, TabGroup, TabList, TabPanel, TabPanels } from '@rgossiaux/svelte-headlessui';
	import Related from './../../../../components/Related.svelte';
	import CartItems from './../../../../components/cartItems.svelte';

	const countries = [
		{ name: 'Afghanistan', code: 'AF' },
		{ name: 'Åland Islands', code: 'AX' },
		{ name: 'Albania', code: 'AL' },
		{ name: 'Algeria', code: 'DZ' },
		{ name: 'American Samoa', code: 'AS' },
		{ name: 'AndorrA', code: 'AD' },
		{ name: 'Angola', code: 'AO' },
		{ name: 'Anguilla', code: 'AI' },
		{ name: 'Antarctica', code: 'AQ' },
		{ name: 'Antigua and Barbuda', code: 'AG' },
		{ name: 'Argentina', code: 'AR' },
		{ name: 'Armenia', code: 'AM' },
		{ name: 'Aruba', code: 'AW' },
		{ name: 'Australia', code: 'AU' },
		{ name: 'Austria', code: 'AT' },
		{ name: 'Azerbaijan', code: 'AZ' },
		{ name: 'Bahamas', code: 'BS' },
		{ name: 'Bahrain', code: 'BH' },
		{ name: 'Bangladesh', code: 'BD' },
		{ name: 'Barbados', code: 'BB' },
		{ name: 'Belarus', code: 'BY' },
		{ name: 'Belgium', code: 'BE' },
		{ name: 'Belize', code: 'BZ' },
		{ name: 'Benin', code: 'BJ' },
		{ name: 'Bermuda', code: 'BM' },
		{ name: 'Bhutan', code: 'BT' },
		{ name: 'Bolivia', code: 'BO' },
		{ name: 'Bosnia and Herzegovina', code: 'BA' },
		{ name: 'Botswana', code: 'BW' },
		{ name: 'Bouvet Island', code: 'BV' },
		{ name: 'Brazil', code: 'BR' },
		{ name: 'British Indian Ocean Territory', code: 'IO' },
		{ name: 'Brunei Darussalam', code: 'BN' },
		{ name: 'Bulgaria', code: 'BG' },
		{ name: 'Burkina Faso', code: 'BF' },
		{ name: 'Burundi', code: 'BI' },
		{ name: 'Cambodia', code: 'KH' },
		{ name: 'Cameroon', code: 'CM' },
		{ name: 'Canada', code: 'CA' },
		{ name: 'Cape Verde', code: 'CV' },
		{ name: 'Cayman Islands', code: 'KY' },
		{ name: 'Central African Republic', code: 'CF' },
		{ name: 'Chad', code: 'TD' },
		{ name: 'Chile', code: 'CL' },
		{ name: 'China', code: 'CN' },
		{ name: 'Christmas Island', code: 'CX' },
		{ name: 'Cocos (Keeling) Islands', code: 'CC' },
		{ name: 'Colombia', code: 'CO' },
		{ name: 'Comoros', code: 'KM' },
		{ name: 'Congo', code: 'CG' },
		{ name: 'Congo, The Democratic Republic of the', code: 'CD' },
		{ name: 'Cook Islands', code: 'CK' },
		{ name: 'Costa Rica', code: 'CR' },
		{ name: "Cote D'Ivoire", code: 'CI' },
		{ name: 'Croatia', code: 'HR' },
		{ name: 'Cuba', code: 'CU' },
		{ name: 'Cyprus', code: 'CY' },
		{ name: 'Czech Republic', code: 'CZ' },
		{ name: 'Denmark', code: 'DK' },
		{ name: 'Djibouti', code: 'DJ' },
		{ name: 'Dominica', code: 'DM' },
		{ name: 'Dominican Republic', code: 'DO' },
		{ name: 'Ecuador', code: 'EC' },
		{ name: 'Egypt', code: 'EG' },
		{ name: 'El Salvador', code: 'SV' },
		{ name: 'Equatorial Guinea', code: 'GQ' },
		{ name: 'Eritrea', code: 'ER' },
		{ name: 'Estonia', code: 'EE' },
		{ name: 'Ethiopia', code: 'ET' },
		{ name: 'Falkland Islands (Malvinas)', code: 'FK' },
		{ name: 'Faroe Islands', code: 'FO' },
		{ name: 'Fiji', code: 'FJ' },
		{ name: 'Finland', code: 'FI' },
		{ name: 'France', code: 'FR' },
		{ name: 'French Guiana', code: 'GF' },
		{ name: 'French Polynesia', code: 'PF' },
		{ name: 'French Southern Territories', code: 'TF' },
		{ name: 'Gabon', code: 'GA' },
		{ name: 'Gambia', code: 'GM' },
		{ name: 'Georgia', code: 'GE' },
		{ name: 'Germany', code: 'DE' },
		{ name: 'Ghana', code: 'GH' },
		{ name: 'Gibraltar', code: 'GI' },
		{ name: 'Greece', code: 'GR' },
		{ name: 'Greenland', code: 'GL' },
		{ name: 'Grenada', code: 'GD' },
		{ name: 'Guadeloupe', code: 'GP' },
		{ name: 'Guam', code: 'GU' },
		{ name: 'Guatemala', code: 'GT' },
		{ name: 'Guernsey', code: 'GG' },
		{ name: 'Guinea', code: 'GN' },
		{ name: 'Guinea-Bissau', code: 'GW' },
		{ name: 'Guyana', code: 'GY' },
		{ name: 'Haiti', code: 'HT' },
		{ name: 'Heard Island and Mcdonald Islands', code: 'HM' },
		{ name: 'Holy See (Vatican City State)', code: 'VA' },
		{ name: 'Honduras', code: 'HN' },
		{ name: 'Hong Kong', code: 'HK' },
		{ name: 'Hungary', code: 'HU' },
		{ name: 'Iceland', code: 'IS' },
		{ name: 'India', code: 'IN' },
		{ name: 'Indonesia', code: 'ID' },
		{ name: 'Iran, Islamic Republic Of', code: 'IR' },
		{ name: 'Iraq', code: 'IQ' },
		{ name: 'Ireland', code: 'IE' },
		{ name: 'Isle of Man', code: 'IM' },
		{ name: 'Israel', code: 'IL' },
		{ name: 'Italy', code: 'IT' },
		{ name: 'Jamaica', code: 'JM' },
		{ name: 'Japan', code: 'JP' },
		{ name: 'Jersey', code: 'JE' },
		{ name: 'Jordan', code: 'JO' },
		{ name: 'Kazakhstan', code: 'KZ' },
		{ name: 'Kenya', code: 'KE' },
		{ name: 'Kiribati', code: 'KI' },
		{ name: "Korea, Democratic People'S Republic of", code: 'KP' },
		{ name: 'Korea, Republic of', code: 'KR' },
		{ name: 'Kuwait', code: 'KW' },
		{ name: 'Kyrgyzstan', code: 'KG' },
		{ name: "Lao People'S Democratic Republic", code: 'LA' },
		{ name: 'Latvia', code: 'LV' },
		{ name: 'Lebanon', code: 'LB' },
		{ name: 'Lesotho', code: 'LS' },
		{ name: 'Liberia', code: 'LR' },
		{ name: 'Libyan Arab Jamahiriya', code: 'LY' },
		{ name: 'Liechtenstein', code: 'LI' },
		{ name: 'Lithuania', code: 'LT' },
		{ name: 'Luxembourg', code: 'LU' },
		{ name: 'Macao', code: 'MO' },
		{ name: 'Macedonia, The Former Yugoslav Republic of', code: 'MK' },
		{ name: 'Madagascar', code: 'MG' },
		{ name: 'Malawi', code: 'MW' },
		{ name: 'Malaysia', code: 'MY' },
		{ name: 'Maldives', code: 'MV' },
		{ name: 'Mali', code: 'ML' },
		{ name: 'Malta', code: 'MT' },
		{ name: 'Marshall Islands', code: 'MH' },
		{ name: 'Martinique', code: 'MQ' },
		{ name: 'Mauritania', code: 'MR' },
		{ name: 'Mauritius', code: 'MU' },
		{ name: 'Mayotte', code: 'YT' },
		{ name: 'Mexico', code: 'MX' },
		{ name: 'Micronesia, Federated States of', code: 'FM' },
		{ name: 'Moldova, Republic of', code: 'MD' },
		{ name: 'Monaco', code: 'MC' },
		{ name: 'Mongolia', code: 'MN' },
		{ name: 'Montserrat', code: 'MS' },
		{ name: 'Morocco', code: 'MA' },
		{ name: 'Mozambique', code: 'MZ' },
		{ name: 'Myanmar', code: 'MM' },
		{ name: 'Namibia', code: 'NA' },
		{ name: 'Nauru', code: 'NR' },
		{ name: 'Nepal', code: 'NP' },
		{ name: 'Netherlands', code: 'NL' },
		{ name: 'Netherlands Antilles', code: 'AN' },
		{ name: 'New Caledonia', code: 'NC' },
		{ name: 'New Zealand', code: 'NZ' },
		{ name: 'Nicaragua', code: 'NI' },
		{ name: 'Niger', code: 'NE' },
		{ name: 'Nigeria', code: 'NG' },
		{ name: 'Niue', code: 'NU' },
		{ name: 'Norfolk Island', code: 'NF' },
		{ name: 'Northern Mariana Islands', code: 'MP' },
		{ name: 'Norway', code: 'NO' },
		{ name: 'Oman', code: 'OM' },
		{ name: 'Pakistan', code: 'PK' },
		{ name: 'Palau', code: 'PW' },
		{ name: 'Palestinian Territory, Occupied', code: 'PS' },
		{ name: 'Panama', code: 'PA' },
		{ name: 'Papua New Guinea', code: 'PG' },
		{ name: 'Paraguay', code: 'PY' },
		{ name: 'Peru', code: 'PE' },
		{ name: 'Philippines', code: 'PH' },
		{ name: 'Pitcairn', code: 'PN' },
		{ name: 'Poland', code: 'PL' },
		{ name: 'Portugal', code: 'PT' },
		{ name: 'Puerto Rico', code: 'PR' },
		{ name: 'Qatar', code: 'QA' },
		{ name: 'Reunion', code: 'RE' },
		{ name: 'Romania', code: 'RO' },
		{ name: 'Russian Federation', code: 'RU' },
		{ name: 'RWANDA', code: 'RW' },
		{ name: 'Saint Helena', code: 'SH' },
		{ name: 'Saint Kitts and Nevis', code: 'KN' },
		{ name: 'Saint Lucia', code: 'LC' },
		{ name: 'Saint Pierre and Miquelon', code: 'PM' },
		{ name: 'Saint Vincent and the Grenadines', code: 'VC' },
		{ name: 'Samoa', code: 'WS' },
		{ name: 'San Marino', code: 'SM' },
		{ name: 'Sao Tome and Principe', code: 'ST' },
		{ name: 'Saudi Arabia', code: 'SA' },
		{ name: 'Senegal', code: 'SN' },
		{ name: 'Serbia and Montenegro', code: 'CS' },
		{ name: 'Seychelles', code: 'SC' },
		{ name: 'Sierra Leone', code: 'SL' },
		{ name: 'Singapore', code: 'SG' },
		{ name: 'Slovakia', code: 'SK' },
		{ name: 'Slovenia', code: 'SI' },
		{ name: 'Solomon Islands', code: 'SB' },
		{ name: 'Somalia', code: 'SO' },
		{ name: 'South Africa', code: 'ZA' },
		{ name: 'South Georgia and the South Sandwich Islands', code: 'GS' },
		{ name: 'Spain', code: 'ES' },
		{ name: 'Sri Lanka', code: 'LK' },
		{ name: 'Sudan', code: 'SD' },
		{ name: 'Suriname', code: 'SR' },
		{ name: 'Svalbard and Jan Mayen', code: 'SJ' },
		{ name: 'Swaziland', code: 'SZ' },
		{ name: 'Sweden', code: 'SE' },
		{ name: 'Switzerland', code: 'CH' },
		{ name: 'Syrian Arab Republic', code: 'SY' },
		{ name: 'Taiwan, Province of China', code: 'TW' },
		{ name: 'Tajikistan', code: 'TJ' },
		{ name: 'Tanzania, United Republic of', code: 'TZ' },
		{ name: 'Thailand', code: 'TH' },
		{ name: 'Timor-Leste', code: 'TL' },
		{ name: 'Togo', code: 'TG' },
		{ name: 'Tokelau', code: 'TK' },
		{ name: 'Tonga', code: 'TO' },
		{ name: 'Trinidad and Tobago', code: 'TT' },
		{ name: 'Tunisia', code: 'TN' },
		{ name: 'Turkey', code: 'TR' },
		{ name: 'Turkmenistan', code: 'TM' },
		{ name: 'Turks and Caicos Islands', code: 'TC' },
		{ name: 'Tuvalu', code: 'TV' },
		{ name: 'Uganda', code: 'UG' },
		{ name: 'Ukraine', code: 'UA' },
		{ name: 'United Arab Emirates', code: 'AE' },
		{ name: 'United Kingdom', code: 'GB' },
		{ name: 'United States', code: 'US' },
		{ name: 'United States Minor Outlying Islands', code: 'UM' },
		{ name: 'Uruguay', code: 'UY' },
		{ name: 'Uzbekistan', code: 'UZ' },
		{ name: 'Vanuatu', code: 'VU' },
		{ name: 'Venezuela', code: 'VE' },
		{ name: 'Viet Nam', code: 'VN' },
		{ name: 'Virgin Islands, British', code: 'VG' },
		{ name: 'Virgin Islands, U.S.', code: 'VI' },
		{ name: 'Wallis and Futuna', code: 'WF' },
		{ name: 'Western Sahara', code: 'EH' },
		{ name: 'Yemen', code: 'YE' },
		{ name: 'Zambia', code: 'ZM' },
		{ name: 'Zimbabwe', code: 'ZW' }
	];

	const FIRST = (e) => {
		e.preventDefault();
		if (browser) {
			document.querySelector('.tick1').classList.replace('block', 'invisible');
			document.querySelector('.tick2').classList.replace('block', 'invisible');
			document.querySelector('.tick3').classList.replace('block', 'invisible');
			document.querySelector('.tick4').classList.replace('block', 'invisible');

			document.getElementById('first').classList.replace('hidden', 'block');
			document.getElementById('second').classList.replace('block', 'hidden');
			document.getElementById('third').classList.replace('block', 'hidden');
			document.getElementById('fourth').classList.replace('block', 'hidden');

			document.getElementById('firstTab').classList.replace(inactive, active);
			document.getElementById('secondTab').classList.replace(active, inactive);
			document.getElementById('thirdTab').classList.replace(active, inactive);
		}
	};

	const SECOND = (e) => {
		e.preventDefault();
		if (browser) {
			document.querySelector('.tick1').classList.replace('invisible', 'block');
			document.querySelector('.tick2').classList.replace('block', 'invisible');
			document.querySelector('.tick3').classList.replace('block', 'invisible');
			document.querySelector('.tick4').classList.replace('block', 'invisible');

			document.getElementById('first').classList.replace('block', 'hidden');
			document.getElementById('second').classList.replace('hidden', 'block');
			document.getElementById('third').classList.replace('block', 'hidden');
			document.getElementById('fourth').classList.replace('block', 'hidden');

			document.getElementById('firstTab').classList.replace(inactive, active);
			document.getElementById('secondTab').classList.replace(active, inactive);
			document.getElementById('thirdTab').classList.replace(active, inactive);
		}
	};

	const THIRD = (e) => {
		e.preventDefault();
		if (browser) {
			document.querySelector('.tick1').classList.replace('invisible', 'block');
			document.querySelector('.tick2').classList.replace('invisible', 'block');
			document.querySelector('.tick3').classList.replace('block', 'invisible');
			document.querySelector('.tick4').classList.replace('block', 'invisible');

			document.getElementById('first').classList.replace('block', 'hidden');
			document.getElementById('second').classList.replace('block', 'hidden');
			document.getElementById('third').classList.replace('hidden', 'block');
			document.getElementById('fourth').classList.replace('block', 'hidden');

			document.getElementById('firstTab').classList.replace(inactive, active);
			document.getElementById('secondTab').classList.replace(active, inactive);
			document.getElementById('thirdTab').classList.replace(active, inactive);
		}
	};

	const FOURTH = (e) => {
		e.preventDefault();
		if (browser) {
			document.querySelector('.tick1').classList.replace('invisible', 'block');
			document.querySelector('.tick2').classList.replace('invisible', 'block');
			document.querySelector('.tick3').classList.replace('invisible', 'block');
			document.querySelector('.tick4').classList.replace('block', 'invisible');

			document.getElementById('first').classList.replace('block', 'hidden');
			document.getElementById('second').classList.replace('block', 'hidden');
			document.getElementById('third').classList.replace('block', 'hidden');
			document.getElementById('fourth').classList.replace('hidden', 'block');

			document.getElementById('firstTab').classList.replace(inactive, active);
			document.getElementById('secondTab').classList.replace(active, inactive);
			document.getElementById('thirdTab').classList.replace(active, inactive);
		}
	};

	const EXPRESS = () => {
		if (browser) {
			document.querySelector('.express').classList.replace('inactive', 'active');
			document.querySelector('.free').classList.replace('active', 'inactive');
		}
	};
	const FREE = () => {
		if (browser) {
			document.querySelector('.express').classList.replace('active', 'inactive');
			document.querySelector('.free').classList.replace('inactive', 'active');
		}
	};

	const cartItems = [
		{
			product: 'Modal-blend Wrap Dress',
			price: 22
		},
		{
			product: 'Flared Satin Skirt',
			price: 63
		},
		{
			product: 'Long-sleeved Wrapover Blouse',
			price: 50
		}
	];

	let subTotalPrice = cartItems.reduce(function (prev, cur) {
		return prev + cur.price;
	}, 0);

	let delivery = 40;
	let total = subTotalPrice + delivery;
</script>

<div class="lg:px-32 px-5 lg:mt-10 mt-5">
	<div class="stepper">
		<div class="flex items-center space-x-2 first">
			<div class="lg:p-2 p-1 border border-black rounded-full">
				<div class="tick1 invisible">
					<div class="progress-circle">
						<TickCircle size={24} color="#fff" variant="Bold" />
					</div>
				</div>
			</div>
			<span class="lg:text-base md:text-left md:text-sm text-xs text-center">Card Details</span>
			<ArrowRight size={16} color="#000" variant="Linear" />
		</div>
		<div class="flex items-center space-x-2 second">
			<div class="lg:p-2 p-1 border border-black rounded-full">
				<div class="tick2 invisible">
					<div class="progress-circle">
						<TickCircle size={24} color="#fff" variant="Bold" />
					</div>
				</div>
			</div>
			<span class="lg:text-base md:text-left md:text-sm text-xs text-center">Shipping Address</span>
			<ArrowRight size={16} color="#000" variant="Linear" />
		</div>
		<div class="flex items-center space-x-2 third">
			<div class="lg:p-2 p-1 border border-black rounded-full">
				<div class="tick3 invisible">
					<div class="progress-circle">
						<TickCircle size={24} color="#fff" variant="Bold" />
					</div>
				</div>
			</div>
			<span class="lg:text-base md:text-left md:text-sm text-xs text-center">Reviews</span>
			<ArrowRight size={16} color="#000" variant="Linear" />
		</div>
		<div class="flex items-center space-x-2 fourth">
			<div class="lg:p-2 p-1 border border-black rounded-full">
				<div class="tick4 invisible">
					<div class="progress-circle">
						<TickCircle size={24} color="#fff" variant="Bold" />
					</div>
				</div>
			</div>
			<span class="lg:text-base md:text-left md:text-sm text-xs text-center">Checkout</span>
		</div>
	</div>

	<div id="first" class="block">
		<div class="lg:grid grid-cols-2 lg:space-y-0 space-y-10">
			<div class="lg:pr-10">
				<form action="">
					<TabGroup class="text-[#575757] my-5">
						<TabList class="flex mb-5 space-x-3 lg:space-x-7 justify-between border-b">
							<Tab
								class={({ selected }) =>
									`${
										selected ? 'selectedd' : 'border-slate-400'
									} text-[#ABABAB] uppercase text-center w-[50%] pb-4 tracking-widest text-sm`}
								>credit card</Tab
							>
							<Tab
								class={({ selected }) =>
									`${
										selected ? 'selectedd' : 'border-slate-400'
									} text-[#ABABAB] uppercase text-center w-[50%] pb-4 tracking-widest text-sm`}
								>paypal</Tab
							>
						</TabList>
						<TabPanels>
							<TabPanel class="form space-y-5">
								<div class="lg:grid grid-cols-2 gap-5 lg:space-y-0 space-y-5">
									<div class="flex flex-col space-y-2">
										<label for="fname">first name</label>
										<input type="text" name="fname" id="fname" placeholder="Tim" class="input" />
									</div>
									<div class="flex flex-col space-y-2">
										<label for="lname">last name</label>
										<input type="text" name="lname" id="lname" placeholder="Panov" class="input" />
									</div>
								</div>
								<div
									class="flex lg:flex-row flex-col lg:items-center lg:space-x-5 lg:space-y-0 space-y-5"
								>
									<div class="flex flex-col space-y-2 lg:w-[80%]">
										<label for="cardNumber">card number</label>
										<input
											type="text"
											name="cardNumber"
											id="cardNumber"
											placeholder="5555 7777 2132 2322"
										/>
									</div>
									<div class="flex flex-col space-y-2 lg:w-[20%]">
										<label for="cvv">cvv</label>
										<input
											type="password"
											maxlength="3"
											name="cvv"
											id="cvv"
											placeholder="914"
											class="input"
										/>
									</div>
								</div>
								<div class="lg:grid grid-cols-2 gap-5 lg:space-y-0 space-y-5 pb-5">
									<div class="flex flex-col space-y-2">
										<label for="exp-date">exp date</label>
										<input
											type="text"
											name="exp-date"
											maxlength="5"
											id="exp-date"
											placeholder="Tim"
											class="input"
										/>
									</div>
									<div class="flex flex-col space-y-2">
										<label for="country">country</label>
										<input
											type="text"
											name="country"
											id="country"
											placeholder="USA"
											class="input"
										/>
									</div>
								</div>
								<button
									class="bg-secondary hover:bg-black transition-colors duration-500 text-white w-full py-2 rounded-full"
									on:click={SECOND}>Buy Now for $170</button
								>
							</TabPanel>
							<TabPanel class="form space-y-5">
								<div class="lg:grid grid-cols-2 gap-5 lg:space-y-0 space-y-5">
									<div class="flex flex-col space-y-2">
										<label for="fname">first name</label>
										<input type="text" name="fname" id="fname" placeholder="Tim" class="input" />
									</div>
									<div class="flex flex-col space-y-2">
										<label for="lname">last name</label>
										<input type="text" name="lname" id="lname" placeholder="Panov" class="input" />
									</div>
								</div>
								<div class="lg:grid grid-cols-2 gap-5 lg:space-y-0 space-y-5">
									<div class="flex flex-col space-y-2">
										<label for="email">email</label>
										<input type="email" name="email" id="email" placeholder="panovtimo@gmail.com" />
									</div>
									<div class="flex flex-col space-y-2">
										<label for="country">country</label>
										<input
											type="text"
											name="country"
											id="country"
											placeholder="USA"
											class="input"
										/>
									</div>
								</div>

								<button
									class="bg-secondary hover:bg-black transition-colors duration-500 text-white w-full py-2 rounded-full"
									on:click={SECOND}>Buy Now for $170</button
								>
							</TabPanel>
						</TabPanels>
					</TabGroup>
				</form>
			</div>
			<div>
				<CartItems />
			</div>
		</div>
	</div>

	<div id="second" class="hidden">
		<div
			class="grid grid-cols-2 uppercase text-gray-200 border-b-2 border-gray-200 pb-2 lg:pb-5 my-5 lg:mb-10"
		>
			<p>delivery details</p>
			<p class="lg:block hidden lg:pl-10">your order</p>
		</div>
		<div class="lg:grid grid-cols-2 lg:space-y-0 space-y-10">
			<div class="form space-y-5">
				<div class="lg:grid grid-cols-2 gap-5 lg:space-y-0 space-y-5">
					<div class="flex flex-col space-y-2">
						<label for="fname">first name</label>
						<input type="text" name="fname" id="fname" placeholder="Tim" class="input" />
					</div>
					<div class="flex flex-col space-y-2">
						<label for="lname">last name</label>
						<input type="text" name="lname" id="lname" placeholder="Panov" class="input" />
					</div>
				</div>
				<div class="flex lg:flex-row flex-col lg:items-center lg:space-x-5 lg:space-y-0 space-y-5">
					<div class="flex flex-col space-y-2 lg:w-[80%]">
						<label for="phone">phone</label>
						<input type="tel" name="phone" id="phone" placeholder="310 - 907 -0012" />
					</div>
					<div class="flex flex-col space-y-2 lg:w-[20%]">
						<label for="postal">postal/zip</label>
						<input
							type="text"
							maxlength="6"
							name="postal"
							id="postal"
							placeholder="90005"
							class="input"
						/>
					</div>
				</div>
				<div class="lg:grid grid-cols-2 gap-5 lg:space-y-0 space-y-5 pb-2">
					<div class="flex flex-col space-y-2">
						<label for="city">city</label>
						<input type="text" name="city" id="city" placeholder="California City" class="input" />
					</div>
					<div class="flex flex-col space-y-2">
						<label for="country">country</label>
						<select
							name="country"
							id="country"
							class="border border-gray-100 bg-transparent rounded-full py-2 px-4 outline-none text-secondary"
						>
							{#each countries as country}
								<option value={country.code}>{country.name}</option>
							{/each}
						</select>
					</div>
				</div>
				<div class="flex flex-col space-y-2">
					<label for="address">Address</label>
					<input
						type="text"
						name="address"
						id="address"
						placeholder="California City, CA 760 Bush St & 20th Ave,..."
						class="input"
					/>
				</div>
				<div class="flex flex-col space-y-2 ">
					<button
						class="bg-secondary hover:bg-black transition-colors duration-500 text-white w-full py-2 rounded-full"
						on:click={THIRD}>Checkout Securely</button
					>
					<!-- svelte-ignore a11y-missing-attribute -->
					<!-- svelte-ignore a11y-click-events-have-key-events -->
					<a
						on:click={FIRST}
						class="text-center underline cursor-pointer underline-offset-4 text-gray-200">Go Back</a
					>
				</div>
			</div>
			<div>
				<div
					class="grid grid-cols-2 uppercase text-gray-200 border-b-2 border-gray-200 pb-2 my-5 md:hidden"
				>
					<p class="lg:block hidden">delivery details</p>
					<p>your order</p>
				</div>
				<CartItems />
			</div>
		</div>
	</div>

	<div id="third" class="hidden">
		<div class="lg:grid grid-cols-2 lg:space-y-0 space-y-10">
			<div>
				<div
					class="flex lg:flex-row flex-col lg:items-center justify-between lg:space-y-0 space-y-3 my-5"
				>
					<p class="font-bold lg:text-4xl text-2xl capitalize">payment</p>
					<div class="flex text-sm">
						<button
							on:click={EXPRESS}
							class="active py-2 px-5 rounded-l-full border-black border-r-none cursor-pointer express"
						>
							Express Delivery <span class="rounded-full bg-gray-200 p-1 text-black">$40</span>
						</button>

						<button
							on:click={FREE}
							class="inactive px-5 py-2 rounded-r-full border border-l-none cursor-pointer free"
						>
							Free Delivery
						</button>
					</div>
				</div>
				<div class="form space-y-5">
					<div class="lg:grid grid-cols-2 gap-5 lg:space-y-0 space-y-5">
						<div class="flex flex-col space-y-2">
							<label for="fname">first name</label>
							<input type="text" name="fname" id="fname" placeholder="Tim" class="input" />
						</div>
						<div class="flex flex-col space-y-2">
							<label for="lname">last name</label>
							<input type="text" name="lname" id="lname" placeholder="Panov" class="input" />
						</div>
					</div>
					<div class="lg:grid grid-cols-2 gap-5 lg:space-y-0 space-y-5">
						<div class="flex flex-col space-y-2">
							<label for="phone">phone</label>
							<input type="tel" name="phone" id="phone" placeholder="219 - 141 -1082" />
						</div>
						<div class="flex flex-col space-y-2">
							<label for="email">email</label>
							<input type="tel" name="email" id="email" placeholder="panovtimo@gmail.com" />
						</div>
					</div>
					<div class="lg:grid grid-cols-2 gap-5 lg:space-y-0 space-y-5">
						<div class="flex flex-col space-y-2">
							<label for="city">city</label>
							<input
								type="text"
								name="city"
								id="city"
								placeholder="California City"
								class="input"
							/>
						</div>
						<div class="flex flex-col space-y-2">
							<label for="country">country</label>
							<select
								name="country"
								id="country"
								class="border border-gray-100 bg-transparent rounded-full py-2 px-4 outline-none text-secondary"
							>
								{#each countries as country}
									<option value={country.code}>{country.name}</option>
								{/each}
							</select>
						</div>
					</div>
					<div class="lg:grid grid-cols-2 gap-5 lg:space-y-0 space-y-5 pb-5">
						<div class="flex flex-col space-y-2">
							<label for="address">Address</label>
							<input
								type="text"
								name="address"
								id="address"
								placeholder="California City, CA 760 Bush St & 20th Ave,..."
								class="input"
							/>
						</div>
						<div class="flex flex-col space-y-2">
							<label for="postal">postal/zip</label>
							<input
								type="text"
								maxlength="6"
								name="postal"
								id="postal"
								placeholder="90006"
								class="input"
							/>
						</div>
					</div>
				</div>
			</div>
			<div class="border-2 border-gray-100 rounded-2xl p-5 lg:px-10 lg:py-10 lg:ml-20">
				<div class="form space-y-5">
					<div class="flex items-center justify-between">
						<h1 class="lg:text-3xl text-xl">Credit Card</h1>
						<div class="flex items-center space-x-2">
							<img src="/visa.png" alt="" class="w-5" />
							<img src="/mastercard.png" alt="" class="w-5" />
							<img src="/paypal.png" alt="" class="w-5" />
						</div>
					</div>
					<div class="">
						<div class="flex flex-col space-y-2">
							<label for="card-name">cardholder name</label>
							<input type="text" name="card-name" id="card-name" class="input" />
						</div>
					</div>

					<div class="lg:flex lg:space-x-5 lg:space-y-0 space-y-5">
						<div class="flex flex-col space-y-2 lg:w-[80%]">
							<label for="card-num">card number</label>
							<input type="text" name="card-num" id="card-num" placeholder="XXXX XXXX XXXX XXXX" />
						</div>
						<div class="flex flex-col space-y-2 lg:w-[20%]">
							<label for="expiry">exp date</label>
							<input type="text" name="expiry" maxlength="5" id="expiry" placeholder="09/24" />
						</div>
					</div>

					<div class="lg:flex lg:space-x-5 lg:space-y-0 space-y-5">
						<div class="flex flex-col space-y-2 lg:w-[20%]">
							<label for="cvv">cvv</label>
							<input type="password" name="cvv" id="cvv" maxlength="3" placeholder="812" />
						</div>
						<div class="flex flex-col space-y-2 lg:w-[80%]">
							<label for="country">country</label>
							<select
								name="country"
								id="country"
								class="border border-gray-100 bg-transparent rounded-full py-2 px-4 outline-none text-secondary"
							>
								{#each countries as country}
									<option value={country.code}>{country.name}</option>
								{/each}
							</select>
						</div>
					</div>

					<div class="flex items-center justify-between lg:text-base text-xs">
						<button on:click={SECOND} class="flex items-center lg:space-x-3 space-x-1">
							<ArrowLeft1 size="16" variant="Linear" />
							<span>Go Back</span>
						</button>
						<button
							class="bg-secondary hover:bg-black transition-colors duration-500 text-white px-5 py-2 rounded-full flex items-center lg:space-x-3 space-x-1"
							on:click={FOURTH}
						>
							<span> Proceed to Checkout</span>
							<ArrowRight1 size="16" color="#fff" variant="Linear" />
						</button>
					</div>
				</div>
			</div>
		</div>
	</div>

	<div id="fourth" class="hidden">
		<div class="lg:grid grid-cols-2 lg:space-y-0 space-y-10 ">
			<div class="space-y-5 pt-10">
				<h3 class="lg:text-3xl text-xl lg:pb-10 pb-5">Confirmation</h3>
				<div class="space-y-3">
					<h4 class="uppercase tracking-widest font-semibold text-sm">delivery</h4>
					<div class="flex items-center space-x-2 text-sm">
						<p class="text-gray-200">30 Valley Lane Los Angeles, CA 90006</p>
						<span class="hover:underline hover:underline-offset-2 cursor-pointer">Edit</span>
					</div>
				</div>
				<div class="space-y-3">
					<h4 class="uppercase tracking-widest font-semibold text-sm">Payment</h4>
					<div class="flex items-center space-x-2 text-sm">
						<p class="text-gray-200 flex items-center space-x-3 bg-[#EBEAED] px-4 py-2 rounded-md">
							<img src="/visa.png" alt="" class="w-5" /> <span>•••• •••• •••• 8781</span>
						</p>
						<span class="hover:underline hover:underline-offset-2 cursor-pointer">Edit</span>
					</div>
				</div>
				<div class="space-y-3">
					<h4 class="uppercase tracking-widest font-semibold text-sm">comment</h4>
					<textarea
						name=""
						id=""
						cols="30"
						rows="5"
						placeholder="Enter your comment"
						class="border border-gray-100 rounded-md py-2 px-4 placeholder:text-sm placeholder:font-light outline-none text-secondary"
					/>
				</div>
			</div>
			<div class="flex space-y-3 lg:justify-end">
				<div class="space-y-3 lg:pt-20">
					<h4 class="uppercase tracking-widest font-semibold text-sm">Shopping Cart</h4>
					{#each cartItems as cartItem}
						<div class="flex items-center space-x-5">
							<div class="flex border-b-2 lg:space-x-32 space-x-5 w-full justify-between py-3">
								<p class="text-gray-100">{cartItem.product}</p>
								<p class="">${cartItem.price}</p>
							</div>
							<div class="rotate-45">
								<Add size="16" color="#000" variant="Linear" />
							</div>
						</div>
					{/each}
					<div class="flex flex-col text-right justify-center mr-10 text-sm space-y-4 my-10">
						<p><span class="text-gray-200 uppercase">Sub-total: </span>${subTotalPrice}</p>
						<p><span class="text-gray-200 uppercase">Express Delivery: </span>${delivery}</p>
						<p><span class="text-gray-200 uppercase">Total: </span>${total}</p>
					</div>
				</div>
			</div>
		</div>
		<div class="flex items-center justify-between lg:text-base text-xs my-10">
			<button
				on:click={THIRD}
				class="flex items-center lg:space-x-3 space-x-1 border rounded-full py-2 px-3"
			>
				<ArrowLeft1 size="16" variant="Linear" />
				<span>Back</span>
			</button>
			<button
				class="bg-secondary hover:bg-black transition-colors duration-500 text-white px-5 py-2 rounded-full"
				on:click={FOURTH}
			>
				<span> Confirm Order</span>
			</button>
		</div>
	</div>
	<div />

	<Related />
</div>
