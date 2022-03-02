<template>
  <div>
    <navbar />
    <main>
      <div
        class="relative pt-16 pb-32 flex content-center items-center justify-center min-h-screen-75"
      >
        <div
          class="absolute top-0 w-full h-full bg-center bg-cover"
          style="
            background-image: url('https://news.files.bbci.co.uk/vj/live/idt-images/image-slider-hello/SMOG_vdyw4.jpg');
          "
        >
         
        </div>
        <div class="container relative mx-auto">
          <div class="items-center flex flex-wrap">
            <div class="w-full lg:w-6/12 px-4 ml-auto mr-auto text-center">
              <div class="pr-12">
                <h1 class="text-white font-semibold text-5xl">
                  भारत
                </h1>
              
              </div>
            </div>
          </div>
        </div>
       
      </div>
          <section class="relative py-16 bg-blueGray-200">
        <div class="container mx-auto px-4">
          <div
            class="relative flex flex-col min-w-0 break-words bg-white w-full mb-6 shadow-xl rounded-lg -mt-64"
          >
            <div class="px-6">
              <div class="flex flex-wrap justify-center">
               
               
                <div class="w-full lg:w-4/12 px-4 lg:order-1">
                  
                </div>
              </div>
              <div class="text-center mt-12">
                <h4
                  class=" font-semibold leading-normal mb-2 text-blueGray-700 mb-2"
                >
                  {{hindiData.article_info_1_byline}}
                </h4>
                <div
                  class="text-sm leading-normal mt-0 mb-2 text-blueGray-400 font-bold uppercase"
                >
                  <i
                    class="fas fa-map-marker-alt mr-2  text-blueGray-400"
                  ></i>
                  {{hindiData.article_info_1_category}}
                  <br />
                  <i
                    class="fas fa-calendar mr-2 text-lg text-blueGray-400"
                  ></i>
                  {{hindiData.article_info_1_date}}
                </div>
                
                <div class="mb-2 text-blueGray-600">
                  <a :href="'{{hindiData.article_info_1_category_url}}'"
                    class="font-normal text-emerald-500"
                  >{{ hindiData.article_info_1_category_url}}</a>
                  
                </div>
              </div>
              <div class="mt-10 py-10 border-t border-blueGray-200 text-center">
                <div class="flex flex-wrap justify-center">
                  <div class="w-full lg:w-9/12 px-4">
                <h3 class="text-3xl mb-2 font-semibold leading-normal">
                {{hindiData.hero_1_title}}
              </h3>
                    <p class="mb-4 text-lg leading-relaxed text-blueGray-700">
                      {{hindiData.p_1_value}}
                    </p >
                     <p v-if="isActive" class="mb-4 text-lg leading-relaxed text-blueGray-700">
                      {{hindiData.p_2_value}}
                    </p>
                     <p v-if="isActive" class="mb-4 text-lg leading-relaxed text-blueGray-700">
                      {{hindiData.p_3_value}}
                    </p>
                     <p v-if="isActive" class="mb-4 text-lg leading-relaxed text-blueGray-700">
                      {{hindiData.p_4_value}}
                    </p>
                     <p v-if="isActive" class="mb-4 text-lg leading-relaxed text-blueGray-700">
                      {{hindiData.p_5_value}}
                    </p>
                  
                    <button
  class="font-normal text-emerald-500"
  :class="[isActive ? 'green' : 'red']"
  @click="toggle"
>{{isActive ? 'Hide' : 'Show More'}}</button>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
      <!-- <br /> -->
     

      <section class="pb-20 bg-blueGray-200 -mt-24">
        <div class="container mx-auto px-4">
          <div class="flex flex-wrap">
           <div class="pt-6 w-full md:w-4/12 px-4 text-center">
              <div
                class="relative flex flex-col min-w-0 break-words bg-white w-full mb-8 shadow-lg rounded-lg"
              >
                <div class="px-4 py-5 flex-auto">
                  <div
                    class="text-white p-3 text-center inline-flex items-center justify-center w-12 h-12 mb-5 shadow-lg rounded-full bg-emerald-400"
                  >
                    <i class="fas fa-award"></i>
                  </div>
                  <h6 class="text-xl font-semibold">सिगरेट का स्तर</h6>
                  <card v-if="selectedCity=='ग़ाज़ियाबाद'" class="font-semibold text-xl text-blueGray-1000">
                    {{hindiData.compare_tabs_1_city_1_cigg}}
                  </card>
                   <card v-show="selectedCity=='नोएडा'" class="font-semibold text-xl text-blueGray-1000">
                    {{hindiData.compare_tabs_1_city_2_cigg}}
                  </card>
                   <card v-if="selectedCity=='दिल्ली'" class="font-semibold text-xl text-blueGray-1000">
                    {{hindiData.compare_tabs_1_city_3_cigg}}
                  </card>
                   <card v-if="selectedCity=='लखनऊ'" class="font-semibold text-xl text-blueGray-1000">
                    {{hindiData.compare_tabs_1_city_4_cigg}}
                  </card>
                   <card v-if="selectedCity=='गुरुग्राम'" class="font-semibold text-xl text-blueGray-1000">
                    {{hindiData.compare_tabs_1_city_5_cigg}}
                  </card>
                   <card v-if="selectedCity=='फ़रीदाबाद'" class="font-semibold text-xl text-blueGray-1000">
                    {{hindiData.compare_tabs_1_city_6_cigg}}
                  </card>
                   <card v-if="selectedCity=='वाराणसी'" class="font-semibold text-xl text-blueGray-1000">
                    {{hindiData.compare_tabs_1_city_7_cigg}}
                  </card>
                   
                   <card v-if="selectedCity=='कानपुर'" class="font-semibold text-xl text-blueGray-1000">
                    {{hindiData.compare_tabs_1_city_8_cigg}}
                  </card>
                   <card v-if="selectedCity=='पटना'" class="font-semibold text-xl text-blueGray-1000">
                    {{hindiData.compare_tabs_1_city_9_cigg}}
                  </card>
                   <card v-if="selectedCity=='मुज़फ़्फ़रपुर'" class="font-semibold text-xl text-blueGray-1000">
                    {{hindiData.compare_tabs_1_city_10_cigg}}
                  </card>
               
                 
             
                </div>
              </div>
            </div>

            <div class="w-full md:w-4/12 px-4 text-center">
              <div
                class="relative flex flex-col min-w-0 break-words bg-white w-full mb-8 shadow-lg rounded-lg"
              >
                <div class="px-4 py-5 flex-auto">
                  <div
                    class="text-white p-3 text-center inline-flex items-center justify-center w-12 h-12 mb-5 shadow-lg rounded-full bg-lightBlue-400"
                  >
                    <i class="fas fa-retweet"></i>
                  </div>
                  <h6 class="text-xl font-semibold">{{hindiData.compare_tabs_1_title}}</h6>
                 
                  <select v-model="selectedCity" @change="cityName">
                    <option disabled value="">{{hindiData.compare_tabs_1_title}}</option>
                    <option v-for="(value, propertyName, index) in hindiCountries" :key="index" :value="value">{{ value }}</option>
                   
                  </select>
                </div>
              </div>
            </div>

            <div class="pt-6 w-full md:w-4/12 px-4 text-center">
              <div
                class="relative flex flex-col min-w-0 break-words bg-white w-full mb-8 shadow-lg rounded-lg"
              >
                <div class="px-4 py-5 flex-auto">
                  <div
                    class="text-white p-3 text-center inline-flex items-center justify-center w-12 h-12 mb-5 shadow-lg rounded-full bg-emerald-400"
                  >
                    <i class="fas fa-fingerprint"></i>
                  </div>
                  <h6 class="text-xl font-semibold">कणिका तत्व </h6>
                  
                  <card v-if="selectedCity=='ग़ाज़ियाबाद'" class="font-semibold text-xl text-blueGray-1000">
                    {{hindiData.compare_tabs_1_city_1_aqi}}
                  </card>
                   <card v-show="selectedCity=='नोएडा'" class="font-semibold text-xl text-blueGray-1000">
                    {{hindiData.compare_tabs_1_city_2_aqi}}
                  </card>
                   <card v-if="selectedCity=='दिल्ली'" class="font-semibold text-xl text-blueGray-1000">
                    {{hindiData.compare_tabs_1_city_3_aqi}}
                  </card>
                   <card v-if="selectedCity=='लखनऊ'" class="font-semibold text-xl text-blueGray-1000">
                    {{hindiData.compare_tabs_1_city_4_aqi}}
                  </card>
                   <card v-if="selectedCity=='गुरुग्राम'" class="font-semibold text-xl text-blueGray-1000">
                    {{hindiData.compare_tabs_1_city_5_aqi}}
                  </card>
                   <card v-if="selectedCity=='फ़रीदाबाद'" class="font-semibold text-xl text-blueGray-1000">
                    {{hindiData.compare_tabs_1_city_6_aqi}}
                  </card>
                   <card v-if="selectedCity=='वाराणसी'" class="font-semibold text-xl text-blueGray-1000">
                    {{hindiData.compare_tabs_1_city_7_aqi}}
                  </card>
                   
                   <card v-if="selectedCity=='कानपुर'" class="font-semibold text-xl text-blueGray-1000">
                    {{hindiData.compare_tabs_1_city_8_aqi}}
                  </card>
                   <card v-if="selectedCity=='पटना'" class="font-semibold text-xl text-blueGray-1000">
                    {{hindiData.compare_tabs_1_city_9_aqi}}
                  </card>
                   <card v-if="selectedCity=='मुज़फ़्फ़रपुर'" class="font-semibold text-xl text-blueGray-1000">
                    {{hindiData.compare_tabs_1_city_10_aqi}}
                  </card>
                  
                </div>
              </div>
            </div>
          </div>

        </div>
      </section>

      <section class="relative py-5">
       
        <div class="container mx-auto px-4">
          <div class="items-center flex flex-wrap">
            <div class="w-full md:w-4/12 ml-auto mr-auto px-4">
              <img
                alt="..."
                class="max-w-full rounded-lg shadow-lg"
                :src="cigar"
              />
              
            </div>
            <div class="w-full md:w-8/12 ml-auto mr-auto px-4">
              <div class="md:pr-12">
                <div
                  class="text-emerald-600 p-3 text-center inline-flex items-center justify-center w-16 h-16 mb-6 shadow-lg rounded-full bg-emerald-300"
                >
                  <i class="fas fa-rocket text-xl"></i>
                </div>
                <h3 class=" font-semibold">{{hindiData.p_6_value}}</h3>
                <p class="mt-4 text-lg leading-relaxed text-blueGray-500">
                  {{hindiData.p_7_value}}
                </p>
                <p class="mt-4 text-lg leading-relaxed text-blueGray-500">
                  {{hindiData.p_8_value}}
                </p>
                <p class="mt-4 text-lg leading-relaxed text-blueGray-500">
                  {{hindiData.p_9_value}}
                </p>
                <p class="mt-4 text-lg leading-relaxed text-blueGray-500">
                  {{hindiData.p_10_value}}
                </p>
               
              </div>
            </div>
          </div>
        </div>
      </section>

 
  
    </main>
    <footer-component />
  </div>
</template>
<script>
import Navbar from "@/components/Navbars/AuthNavbar.vue";
import FooterComponent from "@/components/Footers/Footer.vue";

import team1 from "@/assets/img/team-1-800x800.jpg";
import team2 from "@/assets/img/team-2-800x800.jpg";
import team3 from "@/assets/img/team-3-800x800.jpg";
import team4 from "@/assets/img/team-4-470x470.png";
import cigar from "@/assets/img/ciggrette_icon.png";

export default {
  data() {
    return {
      cigar,
      team1,
      team2,
      team3,
      team4,
      isActive: false,
      selectedCity: '',
      editorialdata : 
{
    "hero_1_image": "https://news.files.bbci.co.uk/vj/live/idt-images/image-slider-hello/SMOG_vdyw4.jpg",
    "hero_1_title": "Delhi smog: How many cigarettes did you smoke this week?",
    "article_info_1_byline": "By me!",
    "article_info_1_date": "20 November 2017",
    "article_info_1_category": "India",
    "article_info_1_category_url": "http://www.bbc.co.uk/news/world/asia/india",
    "p_1_value": "Breathing in Delhi is close to smoking more than a dozen cigarettes a day on an average. Click on your city to find out how many cigarettes you are smoking",
    "total_cities_1_value": "32",
    "p_2_value": "On November 7, Indian capital, Delhi woke up to a blanket of thick grey smog.  The toxic haze was so severe that politicians announced plans to close schools.  United Airlines shut all of its flights from the US to Delhi. Visibility was poor as pollution levels reached 30 times the World Health Organization's recommended limit in some areas.",
    "p_3_value": "According to the data from the System of Air Quality Weather Forecasting and Research website, the levels of tiny particulate matter (known as PM 2.5) that enter deep into the lungs reached as high as 700 micrograms per cubic metre in some areas of Delhi on November 6th. The air quality standard for PM 2.5 is 15 µg/m3 and anything above 81 µg/m3 falls under poor air quality standard.",
    "p_4_value": "Some reports claimed that New Delhi's air quality was so severe it was equivalent to smoking 45 cigarettes a day. We looked at the data to see if this was true. ",
    "p_5_value": "Click on your city to find out how many cigarettes you have effectively smoked because of last week's pollution.",
    "compare_tabs_1_method": "1 cigarette is equivalent to an air pollution of 22 μg/m3 (Absolute value: 21.6 μg/m3) for one day.",
    "compare_tabs_1_title": "Select your city",
    "compare_tabs_1_city_1_name": "Ghaziabad",
    "compare_tabs_1_city_1_aqi": "283 PM2.5",
    "compare_tabs_1_city_1_cigg": "12",
    "compare_tabs_1_city_2_name": "Noida",
    "compare_tabs_1_city_2_aqi": "213 PM2.5",
    "compare_tabs_1_city_2_cigg": "10",
    "compare_tabs_1_city_3_name": "Delhi",
    "compare_tabs_1_city_3_aqi": "235 PM2.5",
    "compare_tabs_1_city_3_cigg": "10",
    "compare_tabs_1_city_4_name": "Lucknow",
    "compare_tabs_1_city_4_aqi": "158 PM2.5",
    "compare_tabs_1_city_4_cigg": "7",
    "compare_tabs_1_city_5_name": "Gurugram",
    "compare_tabs_1_city_5_aqi": "254 PM2.5",
    "compare_tabs_1_city_5_cigg": "11",
    "compare_tabs_1_city_6_name": "Faridabad",
    "compare_tabs_1_city_6_aqi": "220 PM2.5",
    "compare_tabs_1_city_6_cigg": "10",
    "compare_tabs_1_city_7_name": "Varanasi",
    "compare_tabs_1_city_7_aqi": "122 PM2.5",
    "compare_tabs_1_city_7_cigg": "5",
    "compare_tabs_1_city_8_name": "Kanpur",
    "compare_tabs_1_city_8_aqi": "268 PM2.5",
    "compare_tabs_1_city_8_cigg": "12",
    "compare_tabs_1_city_9_name": "Patna",
    "compare_tabs_1_city_9_aqi": "133 PM2.5",
    "compare_tabs_1_city_9_cigg": "6",
    "compare_tabs_1_city_10_name": "Muzaffarpur",
    "compare_tabs_1_city_10_aqi": "114 PM2.5",
    "compare_tabs_1_city_10_cigg": "5",
    "compare_tabs_1_city_11_name": "Mandi Gobindgarh",
    "compare_tabs_1_city_11_aqi": "75 PM2.5",
    "compare_tabs_1_city_11_cigg": "3",
    "compare_tabs_1_city_12_name": "Ludhiana",
    "compare_tabs_1_city_12_aqi": "69 PM2.5",
    "compare_tabs_1_city_12_cigg": "3",
    "compare_tabs_1_city_13_name": "Jodhpur",
    "compare_tabs_1_city_13_aqi": "126 PM2.5",
    "compare_tabs_1_city_13_cigg": "6",
    "compare_tabs_1_city_14_name": "Amritsar",
    "compare_tabs_1_city_14_aqi": "61 PM2.5",
    "compare_tabs_1_city_14_cigg": "3",
    "compare_tabs_1_city_15_name": "Ahmedabad",
    "compare_tabs_1_city_15_aqi": "91 PM2.5",
    "compare_tabs_1_city_15_cigg": "4",
    "compare_tabs_1_city_16_name": "Panchkula",
    "compare_tabs_1_city_16_aqi": "41 PM2.5",
    "compare_tabs_1_city_16_cigg": "2",
    "compare_tabs_1_city_17_name": "Gaya",
    "compare_tabs_1_city_17_aqi": "70 PM2.5",
    "compare_tabs_1_city_17_cigg": "3",
    "compare_tabs_1_city_18_name": "Nagpur",
    "compare_tabs_1_city_18_aqi": "27 PM2.5",
    "compare_tabs_1_city_18_cigg": "1",
    "compare_tabs_1_city_19_name": "Vijaywada",
    "compare_tabs_1_city_19_aqi": "32 PM2.5",
    "compare_tabs_1_city_19_cigg": "1",
    "compare_tabs_1_city_20_name": "Chandrapur",
    "compare_tabs_1_city_20_aqi": "43 PM2.5",
    "compare_tabs_1_city_20_cigg": "1",
    "compare_tabs_1_city_21_name": "Chennai",
    "compare_tabs_1_city_21_aqi": "58 PM2.5",
    "compare_tabs_1_city_21_cigg": "2",
    "compare_tabs_1_city_22_name": "Bhiwadi",
    "compare_tabs_1_city_22_aqi": "103 PM2.5",
    "compare_tabs_1_city_22_cigg": "4",
    "compare_tabs_1_city_23_name": "Mumbai",
    "compare_tabs_1_city_23_aqi": "44 PM2.5",
    "compare_tabs_1_city_23_cigg": "2",
    "compare_tabs_1_city_24_name": "Nashik",
    "compare_tabs_1_city_24_aqi": "51 PM2.5",
    "compare_tabs_1_city_24_cigg": "2",
    "compare_tabs_1_city_25_name": "Thane",
    "compare_tabs_1_city_25_aqi": "41 PM2.5",
    "compare_tabs_1_city_25_cigg": "2",
    "compare_tabs_1_city_26_name": "Aurangabad",
    "compare_tabs_1_city_26_aqi": "48 PM2.5",
    "compare_tabs_1_city_26_cigg": "2",
    "compare_tabs_1_city_27_name": "Hyderabad",
    "compare_tabs_1_city_27_aqi": "56 PM2.5",
    "compare_tabs_1_city_27_cigg": "2",
    "compare_tabs_1_city_28_name": "Visakhapatnam",
    "compare_tabs_1_city_28_aqi": "51 PM2.5",
    "compare_tabs_1_city_28_cigg": "2",
    "compare_tabs_1_city_29_name": "Rajamahandevaram",
    "compare_tabs_1_city_29_aqi": "44 PM2.5",
    "compare_tabs_1_city_29_cigg": "2",
    "compare_tabs_1_city_30_name": "Chittoor",
    "compare_tabs_1_city_30_aqi": "11 PM2.5",
    "compare_tabs_1_city_30_cigg": "0",
    "compare_tabs_1_city_31_name": "Bangalore\n",
    "compare_tabs_1_city_31_aqi": "23 PM2.5",
    "compare_tabs_1_city_31_cigg": "1",
    "compare_tabs_1_city_32_name": "Trivandrum",
    "compare_tabs_1_city_32_aqi": "53 PM2.5",
    "compare_tabs_1_city_32_cigg": "2",
    "p_6_value": "Methodology for calculation: ",
    "p_7_value": "A report by Berkeley Earth showed that in China, 1.6 million people die every year from an average exposure of 52 μg/m3 of PM2.5. To kill 1.6 million people would require, assuming 1.36 x9^6 deaths per cigarette, 1.1 trillion cigarettes. Since the population of China is 1.35 billion, that comes to 764 cigarettes every year per person, or about 2.4 cigarettes per day.",
    "p_8_value": "Put another way, one cigarette is equivalent to an air pollution of 22 μg/m3 (Absolute value: 21.6 μg/m3) for one day.",
    "p_9_value": "The average PM2.5 in Beijing over the year is about 85 μg/m3, equivalent to about 4 cigarettes per day. Similarly, if the air pollution in New Delhi, India, is 546 μg/m3, it is equivalent to about 25 cigarettes each day.",
    "p_10_value": "We took the PM 2.5 data of 33 cities in India every day for one week. We calculated the mean of 6 days PM 2.5 data of each city and divided it by 21.6 μg/m3 to get the number of cigarettes. It is also imperative to say the numbers shown is the assumption that you ideally spent most of your time breathing air from outside."
},
hindiData:{
    "hero_1_image": "https://news.files.bbci.co.uk/vj/live/idt-images/image-slider-hello/SMOG_vdyw4.jpg",
    "hero_1_title": "भारत: इस हफ़्ते आपने आपने कितनी सिगरेट पी हैं?",
    "article_info_1_byline": "By me!",
    "article_info_1_date": "20 November 2017",
    "article_info_1_category": "Hindi",
    "article_info_1_category_url": "http://www.bbc.com/hindi",
    "p_1_value": "दिल्ली में सांस लेना एक दिन में औसतन 25 सिगरेट पीने के बराबर है. अपने शहर पर क्लिक करके देखें कि आप कितनी सिगरेट पी रहे हैं?",
    "total_cities_1_value": "32",
    "p_2_value": "7 नवंबर की सुबह भारत की राजधानी दिल्ली धुंध की चादर से ढकी हुई थी.यह ज़हरीली धुंध इतनी गंभीर थी कि नेताओं को स्कूल बंद करने की घोषणा करनी पड़ी. यूनाइटेड एयरलाइंस ने यूएस से दिल्ली की अपनी सभी फ्लाइट्स बंद कर दीं. विश्व स्वास्थ्य संगठन की निर्धारित सीमा से प्रदूषण का स्तर 30 गुना ज़्यादा पहुंचने से दृश्यता बहुत ख़राब हो गई थी. ",
    "p_3_value": "सिस्टम ऑफ़ एयर क्वालिटी वेदर फॉरकास्टिंग एंड रिसर्च वेबसाइट के आंकड़ों के मुताबिक सूक्ष्म पार्टिक्यूलेट मेटर (पीएम 2.5 के तौर पर जाना जाता है), जो फेफड़ों के अंदर तक चले जाते हैं, का स्तर 7 नवंबर को दिल्ली के कुछ क्षेत्रों में उच्चतम 700 माइक्रोग्राम प्रति घन मीटर पहुंच गया था. ध्यान दें कि पीएम 2.5 के लिए वायु गुणवत्ता मानक 15 माइक्रोग्राम प्रति घन मीटर है और 91 माइक्रोग्राम प्रति घन मीटर से ज्यादा कुछ भी ख़राब वायु गुणवत्ता माना जाता है. ",
    "p_4_value": "कुछ रिपोर्ट्स का दावा है कि नई दिल्ली की वायु गुणवत्ता इतनी गंभीर हो गई थी कि वह एक दिन में 45 सिगरेट पीने के बराबर थी. इसकी सच्चाई जानने के लिए हमने आंकड़े देखे. ",
    "p_5_value": "अपने शहर पर क्लिक करके जानें कि पिछले हफ़्ते के प्रदूषण के कारण आप कितनी सिगरेट पी चुके हैं. ",
    "compare_tabs_1_method": "दूसरे तरीके से देखें तो एक सिगरेट एक दिन के लिए 22 माइक्रोग्राम प्रति घन मीटर (समग्र परिमाण: 21.6 माइक्रोग्राम प्रति घन मीटर) के वायु प्रदूषण के बराबर है.",
    "compare_tabs_1_title": "अपना शहर चुनें ",
    "compare_tabs_1_city_1_name": "ग़ाज़ियाबाद",
    "compare_tabs_1_city_1_aqi": "283 PM2.5",
    "compare_tabs_1_city_1_cigg": "12",
    "compare_tabs_1_city_2_name": "नोएडा",
    "compare_tabs_1_city_2_aqi": "213 PM2.5",
    "compare_tabs_1_city_2_cigg": "10",
    "compare_tabs_1_city_3_name": "दिल्ली",
    "compare_tabs_1_city_3_aqi": "235 PM2.5",
    "compare_tabs_1_city_3_cigg": "10",
    "compare_tabs_1_city_4_name": "लखनऊ",
    "compare_tabs_1_city_4_aqi": "158 PM2.5",
    "compare_tabs_1_city_4_cigg": "7",
    "compare_tabs_1_city_5_name": "गुरुग्राम",
    "compare_tabs_1_city_5_aqi": "254 PM2.5",
    "compare_tabs_1_city_5_cigg": "11",
    "compare_tabs_1_city_6_name": "फ़रीदाबाद",
    "compare_tabs_1_city_6_aqi": "220 PM2.5",
    "compare_tabs_1_city_6_cigg": "10",
    "compare_tabs_1_city_7_name": "वाराणसी",
    "compare_tabs_1_city_7_aqi": "122 PM2.5",
    "compare_tabs_1_city_7_cigg": "5",
    "compare_tabs_1_city_8_name": "कानपुर",
    "compare_tabs_1_city_8_aqi": "268 PM2.5",
    "compare_tabs_1_city_8_cigg": "12",
    "compare_tabs_1_city_9_name": "पटना",
    "compare_tabs_1_city_9_aqi": "133 PM2.5",
    "compare_tabs_1_city_9_cigg": "6",
    "compare_tabs_1_city_10_name": "मुज़फ़्फ़रपुर",
    "compare_tabs_1_city_10_aqi": "114 PM2.5",
    "compare_tabs_1_city_10_cigg": "5",
    "compare_tabs_1_city_11_name": "मंडी गोबिंदगढ़",
    "compare_tabs_1_city_11_aqi": "75 PM2.5",
    "compare_tabs_1_city_11_cigg": "3",
    "compare_tabs_1_city_12_name": "लुधियाना",
    "compare_tabs_1_city_12_aqi": "69 PM2.5",
    "compare_tabs_1_city_12_cigg": "3",
    "compare_tabs_1_city_13_name": "जोधपुर",
    "compare_tabs_1_city_13_aqi": "126 PM2.5",
    "compare_tabs_1_city_13_cigg": "6",
    "compare_tabs_1_city_14_name": "अमृतसर",
    "compare_tabs_1_city_14_aqi": "61 PM2.5",
    "compare_tabs_1_city_14_cigg": "3",
    "compare_tabs_1_city_15_name": "अहमदाबाद",
    "compare_tabs_1_city_15_aqi": "91 PM2.5",
    "compare_tabs_1_city_15_cigg": "4",
    "compare_tabs_1_city_16_name": "पंचकुला",
    "compare_tabs_1_city_16_aqi": "41 PM2.5",
    "compare_tabs_1_city_16_cigg": "2",
    "compare_tabs_1_city_17_name": "गया",
    "compare_tabs_1_city_17_aqi": "70 PM2.5",
    "compare_tabs_1_city_17_cigg": "3",
    "compare_tabs_1_city_18_name": "नागपुर",
    "compare_tabs_1_city_18_aqi": "27 PM2.5",
    "compare_tabs_1_city_18_cigg": "1",
    "compare_tabs_1_city_19_name": "विजयवाड़ा",
    "compare_tabs_1_city_19_aqi": "32 PM2.5",
    "compare_tabs_1_city_19_cigg": "1",
    "compare_tabs_1_city_20_name": "चंद्रपुर",
    "compare_tabs_1_city_20_aqi": "43 PM2.5",
    "compare_tabs_1_city_20_cigg": "1",
    "compare_tabs_1_city_21_name": "चेन्नई",
    "compare_tabs_1_city_21_aqi": "58 PM2.5",
    "compare_tabs_1_city_21_cigg": "2",
    "compare_tabs_1_city_22_name": "भिवाड़ी",
    "compare_tabs_1_city_22_aqi": "103 PM2.5",
    "compare_tabs_1_city_22_cigg": "4",
    "compare_tabs_1_city_23_name": "मुंबई",
    "compare_tabs_1_city_23_aqi": "44 PM2.5",
    "compare_tabs_1_city_23_cigg": "2",
    "compare_tabs_1_city_24_name": "नासिक",
    "compare_tabs_1_city_24_aqi": "51 PM2.5",
    "compare_tabs_1_city_24_cigg": "2",
    "compare_tabs_1_city_25_name": "ठाणे",
    "compare_tabs_1_city_25_aqi": "41 PM2.5",
    "compare_tabs_1_city_25_cigg": "2",
    "compare_tabs_1_city_26_name": "औरंगाबाद",
    "compare_tabs_1_city_26_aqi": "48 PM2.5",
    "compare_tabs_1_city_26_cigg": "2",
    "compare_tabs_1_city_27_name": "हैदराबाद",
    "compare_tabs_1_city_27_aqi": "56 PM2.5",
    "compare_tabs_1_city_27_cigg": "2",
    "compare_tabs_1_city_28_name": "विशाखापट्टनम",
    "compare_tabs_1_city_28_aqi": "51 PM2.5",
    "compare_tabs_1_city_28_cigg": "2",
    "compare_tabs_1_city_29_name": "राजमहानदेवरम",
    "compare_tabs_1_city_29_aqi": "44 PM2.5",
    "compare_tabs_1_city_29_cigg": "2",
    "compare_tabs_1_city_30_name": "चित्तूर",
    "compare_tabs_1_city_30_aqi": "11 PM2.5",
    "compare_tabs_1_city_30_cigg": "0",
    "compare_tabs_1_city_31_name": "बेंगलुरु",
    "compare_tabs_1_city_31_aqi": "23 PM2.5",
    "compare_tabs_1_city_31_cigg": "1",
    "compare_tabs_1_city_32_name": "त्रिवेंद्रम",
    "compare_tabs_1_city_32_aqi": "53 PM2.5",
    "compare_tabs_1_city_32_cigg": "2",
    "p_6_value": "गणना की पद्धति",
    "p_7_value": "बर्कले अर्थ की एक रिपोर्ट दिखाती है ​कि चीन में हर साल पीएम 2.5 के 52 माइक्रोग्राम प्रति घन मीटर के औसतन संपर्क में आने के कारण 16 लाख लोगों की मौत होती है. 16 लाख लोगों के मरने का मतलब होगा, 1.37x10^ 6 मौतें प्रति सिगरेट होना, 11 खरब सिगरेट. जैसे कि चीन की जनसंख्या 1 अरब 35 करोड़ है तो यह हर साल 864 सिगरेट प्रति व्यक्ति या 2.4 सिगरेट प्रति दिन बनता है.",
    "p_8_value": "दूसरे तरीके से देखें तो एक सिगरेट एक दिन के लिए 22 माइक्रोग्राम प्रति घन मीटर (समग्र परिमाण: 21.6 माइक्रोग्राम प्रति घन मीटर) के वायु प्रदूषण के बराबर है.",
    "p_9_value": "पूरे साल में बीजिंग में औसत पीएम 2.5 लगभग 85 माइक्रोग्राम प्रति घन मीटर होता है जो प्रतिदिन करीब चार सिगरेट पीने के बराबर है. इसी तरह, अगर भारत में नई दिल्ली में वायु प्रदूषण 547 माइक्रोग्राम प्रति घन मीटर है तो यह हर दिन 25 सिगरेट पीने के बराबर है.",
    "p_10_value": "हमने भारत के 20 शहरों से एक हफ़्ते तक हर दिन पीएम 2.5 के आंकड़े इकट्ठे किए. हमने हर शहर के पीएम 2.5 आंकड़ों के औसत की गणना की और सिगरेट की संख्या प्राप्त करने के लिए इसे 21.6 माइक्रोग्राम प्रति घन मीटर से भाग कर दिया.यह बताना महत्वपूर्ण है कि दिखाए गए नंबर इस धारणा पर आधारित हैं कि आर्दश रूप से आप अपने अधिकतम समय में बाहर की हवा में सांस लेते हैं."
},
countries:{},
hindiCountries:{}

   
    
      
    };
  },
  components: {
    Navbar,
    FooterComponent,
  },
  methods: {
    toggle() {
  //  this.show = !this.enable;
  this.isActive = this.isActive ? false : true;
},
cityName(){
  console.log("selected citi is",this.selectedCity)
},

extractCountries(){
this.countries = (({ 
                compare_tabs_1_city_1_name, 
                compare_tabs_1_city_2_name, 
                compare_tabs_1_city_3_name,
                compare_tabs_1_city_4_name ,
                compare_tabs_1_city_5_name,
                compare_tabs_1_city_6_name
                }) => ({ 
                  compare_tabs_1_city_1_name, 
                compare_tabs_1_city_2_name, 
                compare_tabs_1_city_3_name,
                compare_tabs_1_city_4_name ,
                compare_tabs_1_city_5_name,
                compare_tabs_1_city_6_name
                }))(this.editorialdata);

                this.hindiCountries = (({ 
                compare_tabs_1_city_1_name, 
                compare_tabs_1_city_2_name, 
                compare_tabs_1_city_3_name,
                compare_tabs_1_city_4_name ,
                compare_tabs_1_city_5_name,
                compare_tabs_1_city_6_name,
                compare_tabs_1_city_7_name,
                compare_tabs_1_city_8_name,
                compare_tabs_1_city_9_name,
                compare_tabs_1_city_10_name,
                }) => ({ 
                  compare_tabs_1_city_1_name, 
                compare_tabs_1_city_2_name, 
                compare_tabs_1_city_3_name,
                compare_tabs_1_city_4_name ,
                compare_tabs_1_city_5_name,
                compare_tabs_1_city_6_name,
                compare_tabs_1_city_7_name,
                compare_tabs_1_city_8_name,
                compare_tabs_1_city_9_name,
                compare_tabs_1_city_10_name,
                }))(this.hindiData);

                // console.log("picked countries", this.countries)
}
  },
  mounted(){
    this.extractCountries()
    console.log("selected citi on lod is",this.selectedCity)
  }
};
</script>
