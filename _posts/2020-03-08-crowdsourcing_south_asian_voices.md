# Crowdsourcing South Asian voices
## Open source speech and text from Mozilla

[A paper](https://arxiv.org/abs/1912.06670) about the Common Voice project was recently accepted to LREC (Language Resources and Evaluation Conference), giving an opportunity to review the project’s progress. Mozilla maintains [voice.mozilla.org](https://voice.mozilla.org/) as a public, multilingual, crowdsourced database of recorded sentences. They can connect this data to two ML projects: speech recognition with [DeepSpeech](https://github.com/mozilla/DeepSpeech), and a [text-to-speech library](https://github.com/mozilla/TTS) based on TacoTron2.

### Representation

> The project was started with an initial focus on English in July 2017 and then in June 2018 was made available for any language.

Though the Common Voice project has been open to languages for some time, more than 40% of the recorded hours (and two-thirds of the individual speakers) are in English.

In mid-2019, recorded languages of South Asia included only Dhivehi (Maldives) and Tamil (South India and Sri Lanka), and Southeast Asia covered Hakha Chin (a minority language in Myanmar) and Indonesian.

More common languages are still stalled, with Hindi [being requested](https://discourse.mozilla.org/t/hindi-locale/36830/4) and UI-localized in Spring 2019 (one year ago).

<img src="/images/cv_hindi_screenshot.png"/>

*If you try to record Hindi today, you are prompted to sign up for e-mail updates*

The presence of minority languages (such as Hakha Chin) is an intentional effort to use Common Voice’s non-commercial, open source platform for recording, rather than depending on major software companies which would own recordings.

In a February 2019 [paper about the Hakha Chin recordings](https://www.researchgate.net/publication/330909775_Building_a_Common_Voice_Corpus_for_Laiholh_Hakha_Chin), Professor Kelly Berkson et. al wrote:

> We decided to pursue Common Voice because we were able to read online about other communities who were involved in the project. We read blog posts about various language groups hosting Common Voice “sprints” focused on collecting a lot of data in a short period of time, and we could envision doing that with our community. We read about the ethics and principles espoused by Common Voice.
[ref](https://medium.com/mozilla-open-innovation/more-common-voices-24a80c879944) We liked the emphasis placed on open access and public domain resources.

Once the project was implemented, local community contacts, churches, and news organizations helped share tutorials to explain how to contribute voices and recordings at home. The team also listened to interesting feedback about the content of the recorded sentences (focusing more on routine appointments and modern technology).

Common Voice’s paper gives special acknowledgement to the contributions of these efforts:

> Common Voice is a living project, and would not be possible without the thousands of hours given by volunteers. We thank all volunteers for their time, and especially the minority language activists who translate, find new texts, and organize Common Voice donation events.

### Timeline of a Successful Project

Though Dhivehi is the national language of the Maldives, it is not commonly served by technology projects. There are an estimated 340,000 speakers worldwide.

The first Twitter mention of the Dhivehi language on Mozilla’s Common Voice was in March 2019:

<a href="https://twitter.com/sofwath/status/1103178291807019008">
<img src="/images/cv_dhivehi_1.png"/>
</a>

Before languages appear on Common Voice, the UI needs to be localized, and representative sentences (as seen above) must be collected from books, Wikipedia articles, and other resources. Translations and sentences also need to be *validated*, a straightforward if less exciting project of reviewing each other’s work.

In my experience with OpenStreetMap, Blockly, and other projects, localizing and validating translations is a delicate stage for an open source project. You need to register translators on an unfamiliar site (Mozilla uses Pontoon; OpenStreetMap is split between TranslateWiki or Transifex). New accounts may need to be validated or added to a team before they can make changes. Then you need multiple active participants to fully complete the translation and check each other’s work. The process does not adapt well to the one-day ‘hackathon’ or ‘weekend side project’ model of volunteering which fuels many open data projects.

By April 2019, the Dhivehi project was open for recordings. Among other Tweets, an appeal was made on the Women in Tech Maldives account:

<a href="https://twitter.com/womenintechmv/status/1117324659198918658">
<img src="/images/cv_dhivehi_2.png"/>
</a>

According to the Mozilla paper, there are now a total of 8 hours of recorded Dhivehi from 92 speakers.
