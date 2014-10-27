# Name

Peyman Mortazavi

# How many points have you earned?

100/100

(Make your own calculation and replace the number 0 with the points you think you've earned.)

# How many hours have you spent on this?

fill-in-your-answer

# When did you first start working on this week's learning challenges?

Saturday

# What is the most difficult part about this week's challenge?

It's hard to tell but I think D3 in general is more difficult for me because I already have some experience with MongoDB.

# Show and tell (8 points)

## Link (2 points)

[Machine Learning floats all boats on Big Data ocean](http://www.infoworld.com/article/2610071/big-data/machine-learning-floats-all-boats-on-big-data-s-ocean.html)

## Discuss how you may apply the machine learning technique mentioned in this article to another interesting problem (6 points).

Well, the article does not really get into details of how machine is actually helping big data. What is interesting is that, according to this article, most algorithms used in machine learning fit the needs for big data because they run even more efficient as the size of the data grows.

# D3 IV

## Checkpoints (3 points x 4 = 12 points)

# 1. (3 points)

![image](/screenshots/checkpoint1.png?raw=true)

[checkpoint](checkpoint1.html)

# 2. (3 points)

![image](/screenshots/checkpoint2.png?raw=true)

[checkpoint](checkpoint2.html)

# 3. (3 points)

![image](/screenshots/checkpoint3.png?raw=true)

[checkpoint](checkpoint3.html)

# 4. (3 points)

![image](/screenshots/checkpoint4.png?raw=true)

[checkpoint](checkpoint4.html)

## Challenges (4 points x 3 = 12 points)

# 1. (4 points)

![image](/screenshots/challenge1.png?raw=true)

# 2. (4 points)

![image](/screenshots/challenge2.png?raw=true)

# 3. (4 points)

![image](/screenshots/challenge3.png?raw=true)

[challenge3](challenge3.html)



# MongoDB II

## Checkpoints (6 points x 2 = 12 points)

### 1 (6 points)

[mongodb js code collecting github events about our course](mongodb-github.js)

### 2 (6 points)

![terminal output of mongodb query](/screenshots/mongo_checkpoint2.png?raw=true)

## Challenge 1 (4 points x 10 = 40 points)

### 1 (4 points)

> db.course_events.findOne( { "actor.login" : "doubleshow" } )

![screenshot](/screenshots/mongo_challenge1.png?raw=true)

### 2 (4 points)

> db.course_events.findOne( { "actor.login" : "doubleshow" }, { actor: 1 } )

![screenshot](/screenshots/mongo_challenge2.png?raw=true)

### 3 (4 points)

> db.course_events.find( {"actor.login": { $in : ["doubleshow", "chrisbopp"] } } , { "actor.login":1, "created_at":1 })

![screenshot](/screenshots/mongo_challenge3.png?raw=true)

### 4 (4 points)

> db.course_events.findOne( {type: 'PushEvent'} )

![screenshot](/screenshots/mongo_challenge4.png?raw=true)

### 5 (4 points)

> db.course_events.find( {type: 'PushEvent'}, { "payload.commits.author.name": 1 } )

![screenshot](/screenshots/mongo_challenge5.png?raw=true)

### 6 (4 points)

> db.course_events.findOne( { type : "IssuesEvent" }, { payload: 1 } )

![screenshot](/screenshots/mongo_challenge6.png?raw=true)

### 7 (4 points)

> db.course_events.find( { type : "IssuesEvent" }, { "payload.issue.user.login": 1 } )

![screenshot](/screenshots/mongo_challenge7.png?raw=true)

### 8 (4 points)

> db.course_events.find( { type : "IssuesEvent", "payload.action" : "closed" }, { "payload.issue.id":1, "payload.issue.state":1 } )

![screenshot](/screenshots/mongo_challenge8.png?raw=true)

### 9 (4 points)

> db.course_events.find({'type' : "IssuesEvent", "payload.issue.state" : "open"}, {"payload.issue.user.login" : 1 , "payload.issue.state" : 1})

![screenshot](/screenshots/mongo_challenge9.png?raw=true)

### 10 (4 points)

> db.course_events.find({'type' : "IssuesEvent", "payload.issue.comments": {$gt:0}}, {"payload.issue.user.login" : 1 , "payload.issue.comments" : 1})

![screenshot](/screenshots/mongo_challenge10.png?raw=true)

## Challenge 2 (8 points x 2 = 16 points) 

### 1 (8 points)

Show forum activities of <user>.

> db.course_events.find({'type' : "IssuesEvent", 'payload.issue.user.login':'<user>'})

![screenshot](/screenshots/mongo_challenge11.png?raw=true)

### 2 (8 points)

What percentage of issues get at least one answer?

> db.course_events.find({'type' : "IssuesEvent", "payload.issue.comments": {$gt:0}}, {"payload.issue.user.login" : 1 , "payload.issue.comments" : 1}).count()/db.course_events.find({'type' : "IssuesEvent", "payload.issue.comments": 0}, {"payload.issue.user.login" : 1 , "payload.issue.comments" : 1}).count() * 100

![screenshot](/screenshots/mongo_challenge12.png?raw=true)
