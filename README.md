# EMAM (Engineer Muhammad Ali Mirza)

Engineer Muhammad Ali Mirza is among the few Islamic scholars and researcher working towards the propagation of true Islamic principles and the unity of Muslim Ummah based on solutions from Quran and Sunnah regardless of any sect or school of thought.

According to him no sect ( Sunni, Shia, Wahabi, Deobandi, Barelvi, Ahl-e-Hadith or whatever) is completely wrong and at the same time not totally correct. There are controversies that have developed due to the scholars of the relevant sects defending their ideologies and hiding the truth from their followers. Engineer Muhammad Ali Mirza highlights and corrects these controversial issues with true references of Quran and Sahih Hadith.

Engineer Muhammad Ali Mirza does not consider any sect as Kaffir except ‘Qadiyani’ (offshoot of Sunni school of thought) and ‘Nusairi’ (offshoot of Shia school of thought).

## Official Cell No

+92-321-5900162. (Call Timings: 09:00 am to 05:00 pm).

## Official Website

[AhleSunnatPak.com](https://www.AhleSunnatPak.com)

## Official YouTube Channels

[Engineer Muhammad Ali Mirza - Official Channel](https://www.youtube.com/user/EngineerMuhammadAliM)  
[Engineer Muhammad Ali Mirza (Complete Lectures Channel)](https://www.youtube.com/user/EngrMuhammadAliMirza)

# This Repository

This is the git repository containing all the timestamps to his lectures on his youtube channel in JSON format. This API is maintained by his student ([me](https://github.com/waleedbutt98)) and is independent of EMAM entirely. This API can be used free of cost with any application and anywhere in the development.

## Usage

The [emam.json](https://github.com/waleedbutt98/EMAM/blob/master/emam.json) file contains the JSON object with keys named after lecture series. Each Lecture series then contains the timestamps according to each lecture in proper format. The format can be of two types based on two types of series.

1. Quran Classes
2. General Lectures (Mas'alah, Majlis etc.)

### 1. Quran Classes

The Quran Classes are of three types:

1. "nqc", which is short for New Quran Class aka [Qura'an Asaan Tarjuma Aur Tafseer](https://www.youtube.com/playlist?list=PLdC3g7t1lPKQIyoPcakbDO3H4Q-BGMpWK)
2. "qc", is short for Quran Class aka [Qura'an Tafseer Lecture (Quran Class)](https://www.youtube.com/playlist?list=PLdC3g7t1lPKTHaO-_ZE04Z9h90oye14t-)

The Quran Classes are formatted in the way, where first key represents the surah number and then its child key represents the Ayat number. Then there is JSON object containing the information regarding that ayat i.e. where that ayat was discussed and mentioned.

```
"nqc": [ <--- Series Name
    { 
      "v": "2zjJbc39qc8", <--- It is the video id of YouTube lecture.
      "timestamps": [ <--- Array of topics in lecture with time
        {
          "t": 0, <--- Time At Which The Topic is Discussed. Compulsory, always a number
          "text": "Anything", <--- Topic which is Discussed. Compulsory, always a string. Will be translation if topic is not critical.
          "type":"ayat", <--- Indicates whether it is a sub topic (undefined) or ayat or intro or critical question,
          "surah": 1, <--- Surah Number of Ayat
          "ayat": 1, <--- Ayat Number of Surah
          "references": [ <--- Array of cross references referred by EMAM.
            {
              "text": "Forex Trading", <--- Video Title
              "v": "v_aG8j1vkNc" <--- YT Video ID.
            }
          ]
        }
      ]
    }
  ]
```

### 2. General Lectures

The general lectures can be of many types where questions are addressed . Most common are:

1. "maslah", which is [Mas'alah Series](https://www.youtube.com/playlist?list=PLdC3g7t1lPKQlQo-qSiTsUbb5Fmv6Whm5)
2. "pqa", which is short for [Public Questions and Answer Session](https://www.youtube.com/playlist?list=PLdC3g7t1lPKQPhJmuzpIRyd2TaFVda5ov)
3. "majlis", which is short for [ILMI-o-Tahqeeqi MAJALIS](https://www.youtube.com/playlist?list=PLdC3g7t1lPKR9C6k-mu8YZY5CYYdmPT9m)
4. "live", which is short for [Live Q & A Session With Engineer Muhammad Ali Mirza | Shahid And Bilal Official](https://www.youtube.com/playlist?list=PLdC3g7t1lPKS_Er5szzZdrNK0SUVFLDtO)
5. "call", which is short for [Ask Questions  With Engineer Muhammad Ali Mirza on Live Video Call | Shahid & Bilal Off](https://www.youtube.com/playlist?list=PLdC3g7t1lPKQax6h7riJCvcVxJXE4nKEf)
6. "critical", which contains videos of EMAM which are not part of any series from his official channel but his recordings with all other kinds of media channels.


The API is a JSON object with each key representing series name. The series name contains JSON object with 'list' key representing the playlist id for youtube playlist where all lectures of relevant series can be found. The lecture series contains array of JSON objects with lectures information and questions addressed.

```
"pqa": [ <--- Series Name
    { 
      "v": "2zjJbc39qc8", <--- It is the video id of YouTube lecture.
      "timestamps": [ <--- Array of topics in lecture with time
        {
          "t": 0, <--- Time At Which The Topic is Discussed. Compulsory, always a number
          "text": "Anything", <--- Topic which is Discussed. Compulsory, always a string
          "other": true, <--- Boolean value, indicating if it should be included in search results.
          "type":"question", <--- Indicates whether it is a sub topic or question, "undefined" indicates sub_topic & "question" indicates question.
          "references": [ <--- Array of cross references referred by EMAM.
            {
              "text": "Forex Trading", <--- Video Title
              "v": "v_aG8j1vkNc" <--- YT Video ID.
            }
          ]
        }
      ]
    }
  ]
```  
NOTE: Each series can be separately downloaded with respective name from any of JSON files.

### 3. Search API  

The search JSON contains the array of all question ever addressed by EMAM. This file can be used to generate search results from his lectures and look for questions addressed within lectures.  
You can see the Demo [here.](https://askemam.pk/).