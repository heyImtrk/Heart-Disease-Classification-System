
domains
 disease,indication = symbol
 patient = string
predicates
 hypothesis(patient,disease)
 symptom(patient,indication)
 response(char)
 go
clauses
 go:-
 write("Enter patient's name ?"),
 readln(Patient),
 hypothesis(Patient,Disease),
 write(Patient," probably has ",Disease,"."),nl.
 go:-
 write("Sorry I dont seem to be able to diagnise the disease"),nl.
 

 symptom(Patient,sweating):-
 write("Does ",Patient," have a sweating problem (y/n)? "),
 response(Reply),
 Reply='y'.

 symptom(Patient,squeezing) :-
 write("Does ",Patient," have a squeezing (y/n)?"),
 response(Reply),
 Reply='y'.

 symptom(Patient,pressure) :-
 write("Does ",Patient," have a pressure (y/n)?"),
 response(Reply),
 Reply='y'.

 symptom(Patient,fullness) :-
 write("Does ",Patient," have a fullness (y/n)?"),
 response(Reply),
 Reply='y'.

symptom(Patient,burning) :-
 write("Does ",Patient,"have burning(y/n)?"),
 response(Reply),
 Reply='y'.

symptom(Patient,breath_shortness) :-
 write("Does ",Patient," have breath_shortness (y/n)?"),
 response(Reply),
 Reply='y'.

symptom(Patient,shortness_breath) :-
 write("Does ",Patient," have a shortness of breath(y/n) ?"),
 response(Reply),
 Reply='y'.

symptom(Patient,fatigue) :-
 write("Does ",Patient," have a fatigue (y/n) ?"),
 response(Reply),
 Reply='y'.

symptom(Patient,weakness) :-
 write("Does ",Patient," have weakness(y/n) ?"),
 response(Reply),
 Reply='y'.

symptom(Patient,chest_pain) :-
 write("Does ",Patient," have chest_pain (y/n) ?"),
 response(Reply),
 Reply='y'.

symptom(Patient,discomfort_in_neck) :-
 write("Does ",Patient," have discomfort_in_neck (y/n) ?"),
 response(Reply),
 Reply='y'.

symptom(Patient,discomfort_in_jaw) :-
 write("Does ",Patient," have discomfort_in_jaw(y/n)? "),
 response(Reply),
 Reply='y'.

symptom(Patient,pain_in_shoulders) :-
 write("Does ",Patient," have pain_in_shoulders(y/n)? "),
 response(Reply),
 Reply='y'.

symptom(Patient,light_headed) :-
 write("Does ",Patient," have light_headed (y/n)? "),
 response(Reply),
 Reply='y'.

symptom(Patient,irregular_heartbeat) :-
 write("Does ",Patient," have irregular_heartbeat(y/n)? "),
 response(Reply),
 Reply='y'.

symptom(Patient,swelling) :-
 write("Does ",Patient," have swelling(y/n)? "),
 response(Reply),
 Reply='y'.

symptom(Patient,lack_of_appetite) :-
 write("Does ",Patient," have lack_of_appetite(y/n)? "),
 response(Reply),
 Reply='y'.

symptom(Patient,chest_fluttering) :-
 write("Does ",Patient," have chest_fluttering(y/n)? "),
 response(Reply),
 Reply='y'.

symptom(Patient,slow_heartbeat) :-
 write("Does ",Patient," have slow_heartbeat(y/n)? "),
 response(Reply),
 Reply='y'.

symptom(Patient,racing_heartbeat) :-
 write("Does ",Patient," have racing_heartbeat(y/n)? "),
 response(Reply),
 Reply='y'.

symptom(Patient,anxiety) :-
 write("Does ",Patient," have anxiety(y/n)? "),
 response(Reply),
 Reply='y'.

symptom(Patient,dizziness) :-
 write("Does ",Patient," have dizziness(y/n)? "),
 response(Reply),
 Reply='y'.

symptom(Patient,lightheadedness) :-
 write("Does ",Patient," have lightheadedness(y/n)? "),
 response(Reply),
 Reply='y'.


hypothesis(Patient,angina):-
 symptom(Patient,sweating),
 symptom(Patient,pressure),
 symptom(Patient,fullness),
 symptom(Patient,burning),
 symptom(Patient,breath_shortness),
 symptom(Patient,fatigue),
 symptom(Patient,weakness).
 
hypothesis(Patient,heart_attack):-
 symptom(Patient,chest_pain),
 symptom(Patient,weakness),
 symptom(Patient,discomfort_in_neck),
 symptom(Patient,discomfort_in_jaw),
 symptom(Patient,breath_shortness),
 symptom(Patient,pain_in_shoulders),
 symptom(Patient,light_headed),
 symptom(Patient,irregular_heartbeat).

hypothesis(Patient,heart_failure):-
 symptom(Patient,chest_pain),
 symptom(Patient,weakness),
 symptom(Patient,swelling),
 symptom(Patient,lack_of_appetite),
 symptom(Patient,chest_fluttering),
 symptom(Patient,irregular_heartbeat).

hypothesis(Patient,heart_arrhythmia):-
 symptom(Patient,weakness),
 symptom(Patient,slow_heartbeat),
 symptom(Patient,racing_heartbeat),
 symptom(Patient,anxiety),
 symptom(Patient,chest_fluttering),
 symptom(Patient,dizziness),
 symptom(Patient,lightheadedness).


response(Reply) :-
 readchar(Reply),
 write(Reply),nl.