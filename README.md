# Brain Watch
This was initially conceived and prototyped at [ArchHacks 2017](https://archhacks.devpost.com/) and won [Most Technically Interesting by Equifax](https://devpost.com/software/brain-watch). Since then we have maintained, updated, and showcased it for Iowa Startup Games, JPEC, and the Hawkeye Accelerator throughout 2018. We call 2019 the lost years, but hopefully 2020 is the year for revival. Stay tuned!

## What is it?
Brain Watch is a connected health platform for players and teams to monitor player brain health both real time(in-game) and post game. In-game a parent or team staff member can monitor player concussion risk in real time, with the hope of preventing further damage to the brain after a traumatic event. With a disease like CTE its the small hits that matter, so the Brain Watch platform keeps record of them and the aggregate effect can be evaluated throughout a players career. In addition, Brain Watch could be scaled down to app level and allow boxers, snowboarders, or other athletes monitor head trauma.

## How to use or contribute
Each part of the stack has their own folder with not very helpful readme's. Feel free to poke around!

---
## More information

### Concussion are an athletes worst nightmare
From snowboarders to martial artists, head trauma is one of the most dangerous injuries possible. This is due in part to the mild nature of the immediate trauma which is largely ignored by the patient. However, concussions are a "fractional injury" that can immediately alter biochemical process in the brain and can lead to neurodegenerative diseases (e.g Parkinson's). While little use to be known about concussions, recent research has unearthed many mysteries surround the injury, and has influenced this project.


### CTE: Football's Dark Side
A recent study found chronic traumatic encephalopathy (CTE)  in 110 out of the 111 studied brains of former NFL players. CTE occurs when repeated head trauma leads to the buildup of "tau," an abnormal protein, in the brain. This neurodegenerative disorder essentially kills brain cells leading to a myriad of neurological symptoms. With more and more parents worrying about their kids out on the field, there is a dire need for real time concussion monitoring. In fact, a prominent physician specializing in concussions has called youth football child abuse. Even more so in the NCAA and the NFL where the stakes are high and underreporting is a huge issue.

## Brain Watch to the Rescue
Brain Watch is a connected health platform for players and teams to monitor player brain health both real time(in-game) and post game. In-game a parent or team staff member can monitor player concussion risk in real time, with the hope of preventing further damage to the brain after a traumatic event. With a disease like CTE its the small hits that matter, so the Brain Watch platform keeps record of them and the aggregate effect can be evaluated throughout a players career. In addition, Brain Watch could be scaled down to app level and allow boxers, snowboarders, or other athletes monitor head trauma.

## How we built it
The IOT device was built using an Arduino 101. We were able process data from it's accelerometer and gyroscope, giving us six degrees of freedom to record from. Player data is held on a MySQL database hosted on AWS RDS, the backend is built using Python (Flask) and NodeJS and is running on Heroku, and the front-end is built using ReactJS. The signal processing uses sophisticated techniques to increase our noise to signal ratio and ultimately use the latest published research mathematical models to evaluate/predict concussion risk.

## Challenges we ran into
We are receiving data at very high velocity with about 3,600,000 data points per sensor per football game so figuring out how to find space to store all this data was difficult as well as how to feed the data in real time to the front end. Of course, the raw data would make no sense to display on the front end so we also had to find an understandable abstraction to show to users that captured the vital information. Most of the data analysis is based around a Stanford study that also used 6-DOF device to compute forces needed to trigger concussions. <i>(Camarillo, D. B., Shull, P. B., Mattson, J., Shultz, R., & Garza, D. (2013). An instrumented mouthguard for measuring linear and angular head impact kinematics in American football. Annals of biomedical engineering, 41(9), 1939-1949.) </i> We used their advanced mathematical models to predict trauma, instantaneously and cumulatively.


## What's next for Brain Watch
We are exploring machine learning methods to help drive knowledge discovery in the trillions of data points collected over a players career. As well as, machine learning methods to classify concussive trauma. We would also like to continue building our hardware to eventually easily fit inside a football helmet.



sources - https://www.si.com/nfl/2017/07/26/nfl-concussion-head-trauma-studies-football-timeline

<i>(Camarillo, D. B., Shull, P. B., Mattson, J., Shultz, R., & Garza, D. (2013). An instrumented mouthguard for measuring linear and angular head impact kinematics in American football. Annals of biomedical engineering, 41(9), 1939-1949.) </i>

<i>McKee, A. C., Cantu, R. C., Nowinski, C. J., Hedley-Whyte, E. T., Gavett, B. E., Budson, A. E., ... & Stern, R. A. (2009). Chronic traumatic encephalopathy in athletes: progressive tauopathy after repetitive head injury. Journal of Neuropathology & Experimental Neurology, 68(7), 709-735.
Chicago</i>
