# Unit 4

## Unit Overview

<table>
    <tr>
        <td>Activity</td>
        <td>Resources</td>
    </tr>
    <tr>
        <td>ToDo</td>
        <td>
            <a href="https://github.com/learn-co-curriculum/hs-advanced-software-engineering-day-4-todo">Day 4 ToDo</a>
            <br>
            <a href="https://github.com/learn-co-curriculum/oo-whale-of-a-time">OO Whale</a>
        </td>
    </tr>
    <tr>
        <td>Amazon Tables Challenge</td>
        <td>
            Tell the students that someone's dropped Amazon's database, and they've been hired to recreate it! Spend 30 minutes creating as many tables as possible. <br>
            <a href="https://github.com/learn-co-curriculum/hs-amazon-tables-challenge">Lab: Amazon Tables Challenge</a><br>
        </td>
    </tr>
    <tr>
        <td>Intro to ActiveRecord relationships/Dynamic URLs</td>
        <td>
            <a href="lectures/intro-to-activerecord-relationships/LECTURE.md">Lecture Guides: Intro to ActiveRecord Relationships</a>
            <br>
            <a href="lectures/intro-to-activerecord-relationships">Lecture Notes</a>
            <br>
            <a href="lectures/dynamic_urls/LECTURE.md">Lecture Guide: Dynamic URLs</a>
            <br>
            <a href="lectures/dynamic_urls">Lecture Notes</a>
            <br>
            <a href="https://github.com/learn-co-curriculum/hs-advanced-software-engineering-fwitter-project/tree/day04-activerecord-relationships">Completed Day 4 Fwitter</a><br>
            <a href="https://github.com/learn-co-curriculum/hs-fwitter-3-databases"> Student Facing Fwitter</a>
        </td>
    </tr>
    <tr>
        <td>Setting up Users and Tweets in Group Project + Fwitter + Labs</td>
        <td>
            <a href="https://github.com/learn-co-curriculum/hs-social-media-recreation-part-3"> Group Project: Adding Users and Associations to our Social Media Recreation</a></br>
            <a href="https://github.com/learn-co-curriculum/hs-advanced-software-engineering-snapchat"> Snapchat Lab</a></br>
            <a href="https://github.com/learn-co-curriculum/OO-my-pets">Lab: OO My Pets</a></br>
            <a href="https://github.com/learn-co-curriculum/jukebox-cli">Lab: OO CLI Jukebox</a></br>
            <a href="https://github.com/learn-co-curriculum/playlister-sinatra">Lab: Playlister Sinatra</a></br>
            <a href="https://github.com/learn-co-curriculum/hs-fwitter-ar-relationships-lab">Stretch Lab: Direct Messages</a>
        </td>
    </tr>

    <tr>
        <td>Wrap Up</td>
        <td>
            <a href="https://github.com/learn-co-curriculum/activerecord-crud">Code Challenge: ActiveRecord CRUD</a>
        </td>
    </tr>
</table>

## SWBATS

### MVC

+ Build model, view and controller for an additional model (Users)

### ActiveRecord

+ Set up has_many/belongs_to relationships
+ Understand how has_many/belongs_to works via a `user_id` column (or similar equivalent for other models)
+ Build up and down migrations to both create and modify tables

### Forms

+ Build forms for something like tweets that connect a tweet object to the user it belongs to
+ Build a sign up form for new users
+ Layout.erb

### MVC

+ Create a sign up POST controller that works with the sign up form to create new users
+ Create a `layout.erb` template and understand how the Ruby keyword `yield` is used within `layout.erb` to render partials
+ Advanced Students - start thinking about how to create another model to track user's followers or start using ActiveRecord validations?
