<script>
	import { lang } from '$lib/stores/LangStore.js';
	import langs from '$lib/localization.json';

	import Socials from '$lib/Socials.svelte';
	import Pill from '$lib/Pill.svelte';
	import PillButton from '$lib/PillButton.svelte';
	import Value from '$lib/Value.svelte';
	import VideoPlayer from '$lib/VideoPlayer.svelte';
</script>

<svelte:head>
	<script type="application/ld+json">
		{
			"@context": "https://schema.org",
			"@type": "Festival",
			"name": "DHOGH Festival 2025",
			"startDate": "2025-06-18",
			"endDate": "2025-06-20",
			"location": {
				"@type": "Place",
				"name": "Žižkárna",
				"url": "https://zizkarna.cz",
				"address": {
					"@type": "PostalAddress",
					"streetAddress": "Žižkova tř. 28",
					"addressLocality": "České Budějovice",
					"addressCountry": "CZ"
				}
			},
			"description": "Festival propojuje taneční hudbu, umění, filozofii a komunitního ducha undergroundové scény. Poskytuje nejen kulturní zážitek, ale i prostor pro hlubší reflexi nad významem elektronické hudby a jejího vlivu na městský noční život.",
			"eventSchedule": [
				{
					"@type": "Event",
					"name": "Středa - Local DJs, Ableton Workshop, DJ Workshop",
					"startDate": "2025-06-18",
					"location": {
						"@type": "Place",
						"name": "Žižkárna",
						"url": "https://zizkarna.cz",
						"address": {
							"@type": "PostalAddress",
							"streetAddress": "Žižkova tř. 28",
							"addressLocality": "České Budějovice",
							"addressCountry": "CZ"
						}
					},
					"performer": [
						{
							"@type": "MusicGroup",
							"name": "body_bass"
						},
						{
							"@type": "Person",
							"name": "antonin_padrta"
						},
						{
							"@type": "Event",
							"name": "DJ Workshop"
						}
					]
				},
				{
					"@type": "Event",
					"name": "Čtvrtek - Live Sets, Synth Workshop",
					"startDate": "2025-06-19",
					"location": {
						"@type": "Place",
						"name": "Žižkárna",
						"url": "https://zizkarna.cz",
						"address": {
							"@type": "PostalAddress",
							"streetAddress": "Žižkova tř. 28",
							"addressLocality": "České Budějovice",
							"addressCountry": "CZ"
						}
					},
					"performer": [
						{
							"@type": "MusicGroup",
							"name": "Jadran"
						},
						{
							"@type": "Person",
							"name": "mista_humix"
						},
						{
							"@type": "MusicGroup",
							"name": "BIOTOP"
						},
						{
							"@type": "Person",
							"name": "Tom_Holič"
						},
						{
							"@type": "Organization",
							"name": "Synth Library Prague"
						}
					]
				},
				{
					"@type": "Event",
					"name": "Pátek - Open Air (17:00-22:00)",
					"startDate": "2025-06-20T17:00",
					"endDate": "2025-06-20T22:00",
					"location": {
						"@type": "Place",
						"name": "Žižkárna",
						"url": "https://zizkarna.cz",
						"address": {
							"@type": "PostalAddress",
							"streetAddress": "Žižkova tř. 28",
							"addressLocality": "České Budějovice",
							"addressCountry": "CZ"
						}
					},
					"performer": [
						{
							"@type": "Person",
							"name": "TIGERHEAD",
							"sameAs": "https://ra.co/dj/tigerhead"
						},
						{
							"@type": "Person",
							"name": "ALEX_WILCOX",
							"sameAs": "https://www.discogs.com/artist/8125675-Alex-Wilcox"
						},
						{
							"@type": "Person",
							"name": "WNCHNZ"
						},
						{
							"@type": "Person",
							"name": "Surrealita",
							"sameAs": "https://ra.co/dj/surrealita"
						},
						{
							"@type": "Person",
							"name": "Dj_Alyaz",
							"sameAs": "https://ra.co/dj/djalyaz"
						},
						{
							"@type": "Person",
							"name": "Mor4m"
						},
						{
							"@type": "Person",
							"name": "VEIT B",
							"sameAs": "https://soundcloud.com/veit-b"
						},
						{
							"@type": "Person",
							"name": "tvyks"
						}
					]
				}
			],
			"offers": [
				{
					"@type": "Offer",
					"name": "Full Festival Pass",
					"description": "Vstupenka na všechny festivalové dny včetně páteční afterparty",
					"price": "500",
					"priceCurrency": "CZK",
					"availability": "https://schema.org/InStock",
					"url": "https://goout.net/cs/dhogh-festival-2025/szjdaux/"
				},
				{
					"@type": "Offer",
					"name": "Friday Open Air",
					"description": "Vstupenka na páteční program na hlavní stage, kde vystoupí oba headlineři",
					"price": "300",
					"priceCurrency": "CZK",
					"availability": "https://schema.org/InStock",
					"url": "https://goout.net/cs/dhogh-festival-2025/szjdaux/"
				},
				{
					"@type": "Offer",
					"name": "Wormuper (Středa/Čtvrtek)",
					"description": "Vstupenka na středeční a čtvrteční program zaměřený na vzdělávání a komunitu",
					"price": "100-200",
					"priceCurrency": "CZK",
					"availability": "https://schema.org/InStock",
					"url": "https://goout.net/cs/dhogh-festival-2025/szjdaux/"
				}
			],
			"organizer": {
				"@type": "Organization",
				"name": "DHOGH Team",
				"email": "dhoghteam@gmail.com",
				"url": "https://dhogh.com"
			},
			"image": [
				"https://dhogh.com/imgs/artists/alex.jpg",
				"https://dhogh.com/imgs/artists/tigerhead.jpg",
				"https://dhogh.com/imgs/artists/wnchnz.jpg",
				"https://dhogh.com/imgs/values.jpg"
			],
			"url": "https://dhogh.com"
		}
	</script>
</svelte:head>

<div class="content-block black">
	<div class="lang-btn-wrapper">
		<button onclick={() => lang.set($lang === 'cs' ? 'en' : 'cs')}>
			<Pill hoverfx={true} label={$lang === 'cs' ? 'en' : 'cz'} />
		</button>
	</div>
	<svg
		width="1280"
		height="378"
		viewBox="0 0 1280 378"
		fill="none"
		xmlns="http://www.w3.org/2000/svg"
	>
		<g clip-path="url(#clip0_2011_1532)">
			<path
				d="M-226 373.79C-208.36 355.846 -194.781 319.943 -194.781 264.504V113.512C-194.781 58.0726 -208.36 22.1694 -226 4.22575H-53.6296C105.86 4.22575 153.481 78.6652 153.481 188.472C153.481 299.335 105.86 373.774 -53.6296 373.774H-226V373.79ZM-86.1969 366.395H-65.1622C26.4482 366.395 41.5025 278.222 41.5025 188.472C41.5025 100.835 26.4482 11.6051 -65.1622 11.6051H-86.1969V366.379V366.395Z"
				fill="#FFC800"
			/>
			<path
				d="M1506 4.22575H1342.04C1359.68 22.1694 1373.26 58.0726 1373.26 113.512V171.332C1348.11 160.232 1319.42 154.161 1289.75 154.161H1230.65C1223.74 141.689 1219.89 127.955 1219.89 113.512C1219.89 58.0726 1233.47 22.1852 1251.11 4.22575H1087.15C1125.65 45.0327 1151.38 99.3998 1157.69 159.885C1158.69 169.456 1159.24 179.169 1159.24 189.008C1159.24 261.524 1131.77 326.739 1087.32 373.79H1251.09C1233.45 355.846 1219.87 319.943 1219.87 264.504V206.684C1245.02 217.784 1273.71 223.855 1303.38 223.855H1362.49C1369.39 236.327 1373.24 250.061 1373.24 264.504C1373.24 319.943 1359.66 355.831 1342.02 373.79H1505.79C1461.34 326.739 1433.87 261.524 1433.87 189.008C1433.87 116.934 1461.39 51.4974 1505.98 4.22575H1506ZM1352.21 216.46C1301.44 216.46 1257.39 194.195 1235.2 161.556H1240.89C1291.67 161.556 1335.71 183.82 1357.9 216.46H1352.21Z"
				fill="#FFC800"
			/>
			<path
				d="M536.516 4.22575H372.553C390.193 22.1694 403.772 58.0726 403.772 113.512V171.332C378.629 160.232 349.932 154.161 320.268 154.161H261.161C254.261 141.689 250.406 127.955 250.406 113.512C250.406 58.0726 263.985 22.1852 281.625 4.22575H117.662C156.162 45.0327 181.892 99.3998 188.206 159.885C189.205 169.456 189.761 179.169 189.761 189.008C189.761 261.524 162.286 326.739 117.837 373.79H281.609C263.969 355.846 250.39 319.943 250.39 264.504V206.684C275.533 217.784 304.23 223.855 333.894 223.855H393.001C399.902 236.327 403.756 250.061 403.756 264.504C403.756 319.943 390.177 355.831 372.537 373.79H536.31C491.861 326.739 464.386 261.524 464.386 189.008C464.386 116.934 491.909 51.4974 536.5 4.22575H536.516ZM382.722 216.46C331.959 216.46 287.907 194.195 265.714 161.556H271.409C322.187 161.556 366.224 183.82 388.417 216.46H382.722Z"
				fill="#FFC800"
			/>
			<path
				d="M733.871 353.781C648.13 353.781 640.484 280.603 640.484 189.008C640.484 98.3434 647.702 24.235 733.427 24.235C755.937 24.235 773.053 29.3595 786.125 38.489C788.79 35.8874 791.534 33.3961 794.389 30.9994C766.518 11.4158 728.922 0 679.603 0C545.225 0 498.968 85.0039 498.968 189.008C498.968 294.068 545.907 378.016 680.285 378.016C729.35 378.016 766.724 366.647 794.453 347.19C791.597 344.793 788.853 342.286 786.172 339.7C773.196 348.735 756.206 353.797 733.871 353.797V353.781Z"
				fill="#FFC800"
			/>
			<path
				d="M759.522 209.443C759.601 210.594 759.696 211.745 759.776 212.896C759.934 215.104 760.109 217.311 760.315 219.503C760.426 220.638 760.553 221.773 760.68 222.893C760.918 225.084 761.172 227.276 761.457 229.452C761.6 230.524 761.759 231.581 761.917 232.637C762.251 234.876 762.599 237.1 762.98 239.307C763.139 240.253 763.313 241.199 763.488 242.145C763.916 244.479 764.392 246.781 764.884 249.067C765.058 249.856 765.233 250.644 765.407 251.417C765.978 253.908 766.597 256.368 767.232 258.812C767.374 259.364 767.517 259.931 767.676 260.483C768.437 263.258 769.262 266.002 770.119 268.714C770.182 268.919 770.246 269.124 770.309 269.313C779.89 298.878 795.944 324.185 819.898 342.917C820.723 343.563 821.547 344.226 822.404 344.856C823.594 345.739 824.815 346.606 826.053 347.474C826.989 348.12 827.924 348.767 828.876 349.397C830.114 350.217 831.351 351.021 832.62 351.81C833.651 352.441 834.714 353.071 835.777 353.686C837.03 354.427 838.283 355.168 839.568 355.862C840.853 356.556 842.186 357.218 843.518 357.896C845.517 358.905 847.547 359.883 849.625 360.829C851.101 361.491 852.56 362.169 854.083 362.8C855.32 363.32 856.605 363.793 857.874 364.298C859.334 364.865 860.809 365.433 862.316 365.969C863.601 366.427 864.902 366.868 866.218 367.309C867.821 367.83 869.439 368.334 871.073 368.823C872.342 369.202 873.611 369.596 874.911 369.943C876.863 370.479 878.861 370.983 880.86 371.472C881.891 371.724 882.907 371.993 883.969 372.245C886.999 372.923 890.093 373.554 893.234 374.121C894.217 374.295 895.232 374.437 896.232 374.61C898.548 374.988 900.88 375.351 903.259 375.682C904.512 375.856 905.797 375.998 907.082 376.155C909.303 376.423 911.556 376.66 913.84 376.865C915.157 376.991 916.473 377.101 917.806 377.196C920.249 377.385 922.739 377.527 925.246 377.653C926.435 377.716 927.609 377.779 928.815 377.827C932.543 377.968 936.318 378.047 940.173 378.047C955.56 378.047 969.79 376.928 982.94 374.799C989.524 373.727 995.821 372.418 1001.87 370.857C1013.95 367.735 1024.98 363.651 1035 358.7C1090.18 331.454 1115.27 278.001 1120.43 214.82H940.141C940.141 216.255 940.601 217.469 941.426 218.494C942.79 220.197 945.17 221.348 948.121 221.994L1078.26 223.555C1081.91 224.359 1084.69 226.535 1085.77 229.231C1086.13 230.13 1086.29 231.092 1086.24 232.07C1085.78 240.821 1085.12 249.272 1084.15 257.393C1083.67 261.445 1083.12 265.418 1082.48 269.297C1081.85 273.176 1081.13 276.945 1080.33 280.618C1079.52 284.292 1078.61 287.856 1077.61 291.325C1076.61 294.778 1075.5 298.121 1074.28 301.353C1073.68 302.961 1073.03 304.554 1072.36 306.099C1071.03 309.205 1069.57 312.185 1067.98 315.024C1065.6 319.297 1062.95 323.27 1059.97 326.913C1057.99 329.341 1055.85 331.627 1053.58 333.756C1051.3 335.884 1048.87 337.871 1046.27 339.684C1043.67 341.498 1040.9 343.153 1037.97 344.651C1026.23 350.596 1011.73 353.844 993.807 353.844C983.083 353.844 973.597 352.693 965.174 350.517C958.86 348.877 953.165 346.67 948.009 343.91C946.296 342.996 944.631 342.018 943.044 340.977C931.861 333.724 923.58 323.617 917.457 311.239C915.712 307.707 914.126 303.986 912.714 300.092C910.588 294.258 908.827 288.029 907.352 281.454C905.892 274.879 904.719 267.973 903.799 260.767C903.18 255.958 902.672 251.022 902.26 245.961C901.847 240.9 901.514 235.728 901.26 230.446C901.007 225.163 900.816 219.771 900.689 214.299C900.499 206.084 900.436 197.649 900.436 189.071C900.436 163.575 901.007 139.371 903.735 117.785C904.338 112.992 905.052 108.309 905.892 103.783C907.146 96.9874 908.684 90.5068 910.556 84.4047C911.809 80.3366 913.205 76.4262 914.76 72.6893C916.33 68.9523 918.06 65.4046 919.979 62.0303C921.898 58.6718 923.992 55.4867 926.309 52.5223C927.467 51.0402 928.656 49.6053 929.925 48.2335C943.742 33.065 963.936 24.2981 993.41 24.2981C1014.78 24.2981 1031.32 28.8707 1044.13 37.1646C1045.28 37.9214 1046.43 38.694 1047.52 39.514C1056.34 46.026 1063.22 54.446 1068.6 64.4585C1069.27 65.7042 1069.92 66.9814 1070.55 68.2901C1071.81 70.8918 1072.96 73.588 1074.03 76.3789C1074.57 77.7665 1075.07 79.1856 1075.58 80.6362C1079.55 92.1467 1082.2 105.076 1083.96 119.078H1113.02C1110.66 110.358 1107.78 101.954 1104.36 93.9284C1102.64 89.9234 1100.79 85.9973 1098.79 82.1815C1097.79 80.2736 1096.76 78.3972 1095.7 76.5366C1093.56 72.8312 1091.27 69.2204 1088.84 65.7199C1086.42 62.2195 1083.83 58.8452 1081.1 55.5655C1078.37 52.3016 1075.49 49.148 1072.44 46.1364C1067.87 41.6111 1062.97 37.3538 1057.69 33.4118C1052.41 29.4699 1046.76 25.8276 1040.71 22.5321C1036.69 20.3246 1032.5 18.2748 1028.13 16.3669C1004.05 5.8183 974.787 0 939.523 0C935.652 0 931.892 0.0946064 928.165 0.220748C926.975 0.268052 925.817 0.34689 924.643 0.394194C922.121 0.520335 919.614 0.662245 917.171 0.851458C915.855 0.946064 914.554 1.07221 913.253 1.18258C910.937 1.40333 908.669 1.63985 906.416 1.9079C905.179 2.04981 903.925 2.19172 902.704 2.36516C900.213 2.69628 897.77 3.09048 895.359 3.50044C894.487 3.64235 893.583 3.76849 892.71 3.92617C889.537 4.50957 886.412 5.14028 883.367 5.83406C882.383 6.05481 881.447 6.3071 880.495 6.54361C878.401 7.04818 876.323 7.58428 874.293 8.15192C873.087 8.48304 871.913 8.8457 870.724 9.20836C868.979 9.7287 867.249 10.2806 865.552 10.8482C864.346 11.2424 863.157 11.6524 861.983 12.0781C860.317 12.6773 858.667 13.308 857.049 13.9545C855.955 14.3802 854.844 14.8059 853.766 15.2632C851.703 16.1304 849.689 17.0449 847.69 17.9752C846.421 18.5744 845.184 19.1893 843.93 19.82C842.281 20.6557 840.631 21.4914 839.029 22.3744C837.918 22.9894 836.84 23.6201 835.761 24.2666C834.508 24.9919 833.27 25.733 832.049 26.4898C830.938 27.1836 829.844 27.8931 828.765 28.6027C827.655 29.3438 826.56 30.1006 825.482 30.8575C825.45 30.889 825.418 30.9048 825.37 30.9363C824.324 31.6774 823.261 32.4185 822.229 33.1911C821.103 34.0425 820.009 34.9098 818.914 35.7928C817.946 36.5654 816.979 37.3065 816.043 38.0949C814.52 39.372 813.045 40.7123 811.601 42.0526C810.221 43.3297 808.873 44.6385 807.556 45.963C790.217 63.2917 778.05 84.7516 770.23 109.002C770.182 109.144 770.135 109.286 770.103 109.444C769.214 112.203 768.39 115.01 767.612 117.848C767.469 118.368 767.343 118.905 767.2 119.425C766.549 121.885 765.931 124.376 765.36 126.883C765.185 127.656 765.027 128.428 764.852 129.201C764.36 131.503 763.884 133.805 763.456 136.139C763.282 137.069 763.107 138.015 762.948 138.961C762.568 141.169 762.219 143.376 761.902 145.615C761.743 146.672 761.6 147.712 761.457 148.769C761.172 150.929 760.918 153.105 760.68 155.281C760.553 156.416 760.426 157.535 760.315 158.687C760.109 160.862 759.934 163.054 759.776 165.246C759.696 166.397 759.585 167.532 759.522 168.683C759.379 171.001 759.284 173.351 759.189 175.7C759.141 176.725 759.094 177.75 759.062 178.79C758.967 182.165 758.903 185.555 758.903 188.976C758.903 192.429 758.967 195.851 759.062 199.257C759.094 200.298 759.157 201.307 759.189 202.332C759.284 204.713 759.379 207.078 759.522 209.427V209.443Z"
				fill="#FFC800"
			/>
		</g>
		<defs>
			<clipPath id="clip0_2011_1532">
				<rect width="1732" height="378" fill="white" transform="translate(-226)" />
			</clipPath>
		</defs>
	</svg>

	<div class="cols" style="padding: var(--general-px);">
		<div class="col">
			<p class="f3 tt-uppercase">{langs[$lang].landing.label}</p>
			<p class="f3 tt-uppercase">{langs[$lang].landing.address}</p>
		</div>
		<div class="col">
			<p class="f3 tt-uppercase">{langs[$lang].landing.desc1}</p>
			<p class="f3 tt-uppercase">{langs[$lang].landing.desc2}</p>
		</div>
		<div class="col">
			<Socials />
		</div>
	</div>
</div>

<div class="content-block lead-video-wrapper">
	<VideoPlayer src="vids/landing.mp4" />
</div>

<div class="content-block">
	<img src="imgs/landing.jpg" alt="landing" />
</div>

<div class="content-block yellow padded">
	<div class="programme-label bottom-border-line">
		<Pill label={langs[$lang].programme.pill} />
		<Pill label={langs[$lang].programme.pill2} />
	</div>
	<div class="artists">
		{#each langs[$lang].programme.artists as artist}
			<h2 class="f0 tt-uppercase">{artist}</h2>
		{/each}
		<h2 class="f2 tt-uppercase">{langs[$lang].programme.more}</h2>
	</div>
</div>

<div class="content-block yellow padded tickets">
	<div class="video-wrapper">
		<VideoPlayer src="vids/tickets.mp4" />
	</div>
	<PillButton label={langs[$lang].tickets} />
	<p class="f3 tt-uppercase">{langs[$lang].cta}</p>
</div>

<div class="content-block yellow padded">
	<div class="programme-label bottom-border-line">
		<Pill label={langs[$lang].about.pill} />
	</div>
	<div class="cols" style="padding-top: 3rem;">
		{#each langs[$lang].about.values as value}
			<div class="col">
				<Value {...value} />
			</div>
		{/each}
	</div>
</div>

<footer class="black cols" style="padding: var(--general-px);">
	<div class="col">
		<p>
			<a href="mailto:dhoghteam@gmail.com" class="mail-link f3 tt-uppercase">dhoghteam@gmail.com</a>
		</p>
	</div>
	<div class="col">
		<p class="f3 tt-uppercase">DHOGH TEAM &copy; 2026</p>
	</div>
	<div class="col">
		<Socials />
	</div>
</footer>

<style>
	.content-block {
		position: relative;
		width: 100%;
		min-height: 100vh;
		box-sizing: border-box;
	}

	.content-block.black,
	footer.black {
		background-color: var(--black);
		color: var(--yellow) !important;
	}

	.content-block.yellow {
		background-color: var(--yellow);
		color: var(--black);
	}

	.content-block svg {
		display: block;
		width: 100%;
		height: auto;
		padding: var(--general-px) 0;
		box-sizing: border-box;
	}

	.cols {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		width: 100%;
		box-sizing: border-box;
		align-content: space-between;
		justify-content: space-between;
		gap: 2rem;
	}

	.col {
		display: flex;
		flex-direction: column;
		min-width: 0;
	}

	.col:nth-child(2) {
		align-items: center;
		text-align: center;
	}

	.col:nth-child(3) {
		align-items: flex-end;
		text-align: right;
	}

	.content-block.lead-video-wrapper {
		display: flex;
		align-items: center;
		justify-content: center;
		overflow: hidden;
	}

	.content-block img {
		display: block;
		position: relative;
		width: 100%;
		height: auto;
	}

	.padded {
		padding: var(--general-px);
		width: 100%;
		box-sizing: border-box;
	}

	.programme-label {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;
		gap: 1rem;
	}

	.bottom-border-line {
		padding-bottom: 15px;
		border-bottom: 3px solid var(--black);
	}

	/* .artists {
		padding-top: 2rem;
	}

	.artists h2 {
		margin: 0;
	} */

	.tickets {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	.tickets .video-wrapper {
		width: 40%;
		max-width: 700px;
		padding-bottom: 5rem;
	}

	.lang-btn-wrapper {
		position: absolute;
		width: 100%;
		top: 5px;
		right: 5px;
		display: flex;
		flex-direction: row-reverse;
		z-index: 10;
		box-sizing: border-box;
	}

	.lang-btn-wrapper button {
		all: unset;
		cursor: pointer;
	}

	.mail-link {
		text-decoration: none;
		color: inherit;
		font-weight: 400;
		font-style: normal;
		font-size: 18px;
		line-height: 140%;
		letter-spacing: 0%;
		transition: all 0.17s ease-in-out;
		position: relative;
		display: block;
		word-break: break-word;
	}

	.mail-link:hover {
		color: var(--white);
	}

	/* --------------------------------
	   TABLET
	   -------------------------------- */

	@media (max-width: 1200px) {
		.lang-btn-wrapper {
			position: relative;
		}
	}

	/* --------------------------------
	   SMALL TABLET
	   -------------------------------- */

	@media (max-width: 900px) {
		:global(:root) {
			--general-px: 3rem;
		}

		.cols {
			grid-template-columns: repeat(2, 1fr);
			gap: 3rem 2rem;
		}

		.cols .col:nth-child(3) {
			grid-column: 1 / -1;
			align-items: flex-start;
			text-align: left;
		}

		.tickets .video-wrapper {
			width: 60%;
		}
	}

	/* --------------------------------
	   MOBILE
	   -------------------------------- */

	@media (max-width: 600px) {
		:global(:root) {
			--general-px: 1.25rem;
			--general-px-sm: 1.25rem;
		}

		.content-block {
			min-height: auto;
		}

		/*
		 * Give the first black section enough room
		 * for the logo + information.
		 */
		.content-block.black:first-child {
			padding-bottom: 2rem;
		}

		.content-block svg {
			width: 100%;
			padding: 3rem 0 2rem;
		}

		.cols {
			display: flex;
			flex-direction: column;
			gap: 2rem;
			padding: var(--general-px) !important;
		}

		.col,
		.col:nth-child(2),
		.col:nth-child(3) {
			width: 100%;
			align-items: flex-start;
			text-align: left;
		}

		.col:nth-child(2) {
			align-items: flex-start;
			text-align: left;
		}

		.col:nth-child(3) {
			align-items: flex-start;
			text-align: left;
		}

		.content-block.lead-video-wrapper {
			min-height: auto;
			aspect-ratio: 16 / 9;
		}

		.content-block.lead-video-wrapper :global(video) {
			width: 100%;
			height: 100%;
			object-fit: cover;
		}

		.padded {
			padding: var(--general-px);
		}

		.programme-label {
			flex-direction: column;
			align-items: flex-start;
			justify-content: flex-start;
			gap: 0.5rem;
		}

		.bottom-border-line {
			padding-bottom: 12px;
			border-bottom-width: 2px;
		}

		.artists {
			padding-top: 1.5rem;
		}

		.artists h2 {
			font-size: clamp(2.5rem, 12vw, 5rem);
			line-height: 0.85;
			overflow-wrap: anywhere;
		}

		.artists .f2 {
			margin-top: 1.5rem;
		}

		.tickets {
			min-height: auto;
			padding-top: 3rem;
			padding-bottom: 3rem;
		}

		.tickets .video-wrapper {
			width: 100%;
			padding-bottom: 2rem;
		}

		.tickets :global(video) {
			width: 100%;
			height: auto;
			display: block;
		}

		.mail-link {
			font-size: 16px;
		}

		footer {
			min-height: auto !important;
		}

		footer .cols {
			padding: var(--general-px) !important;
		}
	}

	/* --------------------------------
	   VERY SMALL PHONES
	   -------------------------------- */

	@media (max-width: 400px) {
		:global(:root) {
			--general-px: 1rem;
		}

		.content-block svg {
			padding-top: 2.5rem;
			padding-bottom: 1.5rem;
		}

		.artists h2 {
			font-size: clamp(2.2rem, 12vw, 3.5rem);
		}

		.cols {
			gap: 1.5rem;
		}
	}
</style>
