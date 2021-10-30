
1) SELECT name, weighting
   FROM Course, Assessment
   WHERE Course.cid = Assessment.cid AND title = 'Database systems'
   ORDER BY name;

2)SELECT Course.cid, name, AVG(mark)
  FROM Course, Assessment, Grade
  GROUP BY Course.cid, name;

3a)SELECT Course.cid, Course.title, Assessment.name, Assessment.weighting, Grade.mark 
  FROM Course JOIN Assessment ON Course.cid = Assessment.cid JOIN Grade ON Grade.aid = Assessment.aid 
  WHERE Grade.sid = 'S0001';

3b)SELECT Assessment.cid, 
  SUM(Grade.mark * Assessment.weighting)/SUM(Assessment.weighting) as average 
  FROM Assessment JOIN Grade ON Grade.aid = Assessment.aid 
  WHERE Grade.sid = 'S0001' 
  GROUP BY Assessment.cid;
