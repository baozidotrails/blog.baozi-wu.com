---
layout: post
title: "Nested form with Rails 4.1"
date: 2014-08-18 16:50:01 +0800
comments: true
categories: [Railscasts, Rails, Tips]
---
Recently I got a [guide](http://us5.campaign-archive2.com/?u=0d868b8bb90703d75a27d8b42&id=055f149177&e=eea34cb3a8) of telling us how to be self-taught from online courses. It shows me how important taking note is. I highly recommened this guide to for who also wants to be self-taught.

> The average person forgets 40% of what they learn within 20 minutes.

So I decide to take notes here since now. It will spend most of my time to do, but if I do not do it today, I know I won't do it anymore. That is my lazy personality. The first technical post I am going to present my reviews of [#196 Nested Model Form (revised)](http://railscasts.com/episodes/196-nested-model-form-revised); meanwhile, some of the codes there are not working because of the version of Rails, so I will try to make it work like video shows with the latest Rails, please revise my code if you have better ways, thanks a bunch. Ok, so let us get started.

# The Purpose
Like [#196 Nested Model Form (revised)](http://railscasts.com/episodes/196-nested-model-form-revised) says, there are three models and they already had associations with each other:

``` ruby app/models/survey.rb
class Survey < ActiveRecord::Base
  has_many :questions
end
```

``` ruby app/models/question.rb linenos:false
class Question < ActiveRecord::Base
  belongs_to :survey
  has_many :answers
end
```

``` ruby app/models/answer.rb
class Answer < ActiveRecord::Base
  belongs_to :question
end
```