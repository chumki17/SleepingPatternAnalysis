How much do people sleep?

Social media analysis sheds considerable light on human behavior, gaining statistical strength from the scale of such interactions.    In this project, we will analyze Twitter data to get insight into factors affecting how much sleep different populations receive.

Prof. Jason Jones of Sociology has used Twitter for studying sleep patterns, most notably his study of the performance of NBA basketball players after unusually late nights, as measured by late night tweets.  A good way to start this project is to read his papers on this work, particularly 

JJ Jones, GW Kirschen, S Kancharla, L Hale
Sleep health 5 (1), 68-71
Association between late-night tweeting and next-day game performance among professional basketball players

There are many interesting ways to break down this data.    I am much more interested in projects which do a sophisticated and careful (statistically defensible) analysis of one of these questions than a hack programming job that does a lousy job tabulating all of them.   Possibilities include:

Sunlight and seasonal effects -- The time of sunrise varies with latitude and season. A reasonable hypothesis is that sunrise affects the time people awaken in the morning.   Can you produce a satisfying sleep map video showing wakeup times by place for each (say) week of the year?    Are bedtimes in synch with this, or do people get less sleep in summer and more sleep in winter?    Are their periodic changes in the temperate regions, which have less fluctuation in sunrise/set times than more polar regions?
Weekend and holiday effects -- How do holidays (where people are less likely to travel to work) change people’s sleep schedules, and how long does it take for them to recover?
Time zone effects -- Because time zones are broad, there is more light at 7AM on the eastern side of a time zone than the west.   All presumably work the same conventional hours (traditionally 9AM-5PM).   A reasonable hypothesis is that people on the east end of a time zone wake up earlier than the west -- is this true?
Daylight savings time effects -- How do sleep times adjust to annual one-hour time changes in fall and spring?   Do people gain/lose an hour of sleep, or does it come from other activities?   How long does the change in sleep times last?
Job title effects (*) -- The self-reported description string for each Twitter account gives insight into how people see themselves.   Often it contains information as to career and interests.   Are there differences in the sleep patterns of truckers and teachers?   Prof. Jones has done some work on these strings, but the first task is to classify them into groups.
Age, gender and nationality effects -- Do sleep schedules vary significantly among people of different demographic groups?   Be careful: these effects must be separated from sampling and geographic biases.
Time course effects -- As the years go by, are people getting more or less sleep?   Be careful: these effects must be decoupled from changes in the popularity of Twitter and all the other factors discussed above.
Travel effects -- Geolocation tags and self-reported tweets should identify people who had cross-country travels.     How did this affect their sleep patterns, and for how long?

Large scale Twitter data sets are available on the IACS Seawulf cluster.
Prof Jones has been collecting a 1% sample of all tweets from February 2015 through to the present.  These tweets are stored as text files in JSON format.  Each hour, the collector writes about 100,000 tweets to disk and the hour files are about 100 MB compressed.
The files contain Tweet objects in JSON format.  There is good documentation for these objects available through the Twitter API documentation.  https://developer.twitter.com/en/docs/tweets/data-dictionary/overview/tweet-object.html
Each Tweet object contains a User object.  User objects contain information about the author, including their preferred display time zone, their self-description and a free-response location field.

One days worth of Prof. Jones’ hourly data are available at:

https://drive.google.com/file/d/1A2p8V9O2HKR6KrzJME3ZlNZQyqILFsIp/view?usp=sharing
https://drive.google.com/file/d/1bYH3ooiAKZbg-fiZ8FHHYNiCSA4dYSBb/view?usp=sharing
https://drive.google.com/file/d/1yiotD05mRrZvkFPo8teG4TPuhws_qUVo/view?usp=sharing
https://drive.google.com/file/d/1ITWmOl-i5n8rk-MzNM8lm59nG-mbjD3T/view?usp=sharing
https://drive.google.com/file/d/1eOZlS7PO-ywqMcRptVS-FFYfQhCkTPiN/view?usp=sharing
https://drive.google.com/file/d/17XAk7_FNFlEo14YhYmD2_6SNB_y4MTfZ/view?usp=sharing
https://drive.google.com/file/d/1zo3lcTd2V6Ttt-ylJH4h-iMpZVd_CzF5/view?usp=sharing
https://drive.google.com/file/d/1UtGsytOW7vW0wPwt1cGmaPnCLQ_KMlvS/view?usp=sharing
https://drive.google.com/file/d/1Mbl-BJ1YFhpEJc2Zeefd-wsWQnzd7989/view?usp=sharing
https://drive.google.com/file/d/1LNk2L8blALDILpeexux557p6T2d876XE/view?usp=sharing
https://drive.google.com/file/d/1Sjrq2KEQTDFfVrvDTp_P1oipyULY1y3Q/view?usp=sharing
https://drive.google.com/file/d/1RLmu4JqumjdzbPz18xfmZHiKJu3Ix8lF/view?usp=sharing
https://drive.google.com/file/d/10SSnH8Coq_x6YnIprzbpZPrrEKKSWVZI/view?usp=sharing
https://drive.google.com/file/d/1U-_NRGp5Uls9LJumTnIlTpQtAfY2oyR0/view?usp=sharing
https://drive.google.com/file/d/19ycs2tO9C74FeNA-wU2bMzwjgaFO6pQu/view?usp=sharing
https://drive.google.com/file/d/1-awGVaqo9Vr8lenIcowf-F9oZwUcA824/view?usp=sharing
https://drive.google.com/file/d/1xygxTkZZLQ3QBKll9sYvWDdlwHw1xjAy/view?usp=sharing
https://drive.google.com/file/d/10FTVg4E2hBj7KSLotNerKjD4uL3amkGT/view?usp=sharing
https://drive.google.com/file/d/1In4nUiPMiu4r_ttRv1Fbblr0DBptyP6E/view?usp=sharing
https://drive.google.com/file/d/1GhoTwSI30YflSAE85OCMM1SBXQqZd7-7/view?usp=sharing
https://drive.google.com/file/d/1PfJ0sB0dMFmcna6snDmVtn3A-t-TaPaZ/view?usp=sharing
https://drive.google.com/file/d/1nmrvS1u5e37n_qHb7OSfzunNuDMgVvsE/view?usp=sharing
https://drive.google.com/file/d/1ViJ1yICz2viKiFAbQf8ioHyhQSOublEw/view?usp=sharing
https://drive.google.com/file/d/1AQCgcvwSdlGO6cI35FcmYvlFXfEcZgQV/view?usp=sharing

Twitter data might also be obtainable by your own spidering/download efforts.   For your final analysis, we can pursue access to the IACS cluster for serious teams.

There are many effective ways to mess up your analysis.   Some of these include:

Bots and corporate sources -- Mechanical sources do not sleep according to a human schedule.    Companies are most active during the business day regardless of location or season.   One must try to identify and eliminate such sources.
Sampling effects -- You are only seeing 1% of all posted tweets, which means you are unlikely to see the first and last tweet of the day for people.    An important orthogonal analysis might be to analyze the full profile of a smaller number of people, with limitations imposed by Twitter APIs.
Statistical sharpness - You need the right statistic to pick up the subtle phenomenon of first and last tweet of the day.    Perhaps it is over or under representation in each time window over a baseline, but you need to do some clear thinking to get something meaningful.
