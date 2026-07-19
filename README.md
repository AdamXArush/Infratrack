InfraTrack — Crowdsourcing Road & Infrastructure Damage Application

InfraTrack is a mobile application that helps road users identify road and infrastructure
hazards before or during their journey. Users can view the latest hazard reports and see
known hazards plotted on an interactive map. Hazard data is crowdsourced and managed by an
administrator through a web-based panel, then delivered to the mobile app in real time.

Built for ICT602 Mobile Technology and Development, Universiti Teknologi MARA (UiTM).


Features


Latest hazard feed — road and infrastructure reports shown newest-first (type, location, description, reporter, date & time).
Interactive hazard map — known hazards plotted as markers on Google Maps.
Server-driven markers — markers are downloaded live from the remote database, never hard-coded. New reports appear without reinstalling the app.
Hazard details — tapping a marker shows the hazard type, location, description, reporter, and the date & time it was reported.
Web admin panel — an administrator inputs hazard location, description, and GPS coordinates; entries sync instantly to the database.
Current location — the app shows the user's GPS position on the map.
User feedback — loading indicators and a no-internet notice when data can't be fetched.
About page — app info, developer details, copyright, and project link.



How it works

[ Web Admin Panel ]  --writes-->  [ Firebase Firestore ]  --reads-->  [ Android App ]
   input hazards          the "hazards" collection         news list + map markers

The web panel and the Android app share one Firebase project, so a hazard added by the
admin appears in the app's feed and on the map automatically.


Tech stack


Android — Kotlin, Google Maps SDK for Android
Backend — Firebase Cloud Firestore (real-time database)
Web admin panel — HTML, CSS, JavaScript, Firebase Web SDK
Hosting — Firebase Hosting (web panel)



Project structure

infratrack/
├── android/     # Android application (Kotlin)
└── web/         # Web admin panel (HTML/JS + Firebase)


Data model

Firestore collection: hazards

FieldTypeDescriptionhazardTypestringe.g. Pothole, Flooding, Fallen TreelocationNamestringName of the affected locationdescriptionstringShort description of the hazardlatitudenumberGPS latitudelongitudenumberGPS longitudereporterNamestringWho reported the hazardreportedAttimestampAuto-recorded date & time


Team — Group CDCS240/5A

NoNameStudent ID1Muhamad Afiq Danial bin Abdul Waliyy20247761232Adam bin Arush20245686873Muhammad Fahmi bin Md Saini20247643754Muhammad Syahmi bin Rosman20243942335Siti Nursolehah binti Saufi20249078236Noor Azizah Ain Azila binti Abdul Ghani2024545237

Lecturer: Madam Nor Asma binti Mohd Zin
Course: ICT602 Mobile Technology and Development
Programme: Bachelor of Information Technology (Hons.), UiTM Cawangan Kelantan, Kampus Machang
