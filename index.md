---
layout: home
title: Natural Language Processing
nav_exclude: true
toc: true
seo:
  type: Course
  name: Natural Language Processing
---

# {{ site.tagline }}
{: .fs-7 .fw-350 }
MWF 11:30-12:20pm, CSE2 G10 (Gates, ground floor)
{: .fs-6 .fw-300 }

{% assign instructors = site.staffers | where: 'role', 'Instructor' %}
{% for staffer in instructors %}
{{ staffer }}
{% endfor %}

{% assign teaching_assistants = site.staffers | where: 'role', 'Teaching Assistant' %}
{% assign num_teaching_assistants = teaching_assistants | size %}
{% if num_teaching_assistants != 0 %}

{% for staffer in teaching_assistants %}
{{ staffer }}
{% endfor %}
{% endif %}

<!-- Office hours are available on Zoom by appointment. -->

## Announcements


<!-- - Please fill out [this feedback form](https://forms.gle/dQ5s8e8Satc6Ww797) so we know how to improve. Thank you! -->
  
## Summary

This course will explore foundational statistical techniques for the automatic analysis of natural (human) language text. Towards this end the course will introduce pragmatic formalisms for representing structure in natural language, and algorithms for annotating raw text with those structures. The dominant modeling paradigm is corpus-driven statistical learning, covering both supervised and unsupervised methods. Algorithms for NLP is a lab-based course. This means that instead of homeworks and exams, you will mainly be graded based on three hands-on coding projects.

This course assumes a good background in basic probability and a strong ability to program in Python. Experience using numerical libraries such as NumPy and neural network libraries such as PyTorch are a plus. Prior experience with machine learning, linguistics or natural languages is helpful, but not required. There will be a lot of statistics, algorithms, and coding in this class.

## Calendar

Calendar is tentative and subject to change. More details will be added as the quarter continues.

<table>
  <thead>
  <tr>
    <th>Week</th>
    <th>Date</th>
    <th width="30%">Topics</th>
    <th width="20%">Readings</th>
    <th width="13%">Homeworks</th>
  </tr>
  </thead>
  <tbody>
  {% for week in site.data.calendar %}
    {% for day in week.days %}
      <tr>
        {% if forloop.index == 1 %}
        <td rowspan="{{week.size}}">{{week.week}}</td>
        {% endif %}
        <td>{{day.date}}</td>
        <td class="cal-content">
          {{day.topics}}
          <br>
          {% if day.slides %}
            <a href="{{day.slides}}" class="cal-content-link">[slides]</a>
          {% endif %}
          {% if day.recording %}
            <a href="{{day.recording}}" class="cal-content-link">[recording]</a>
          {% endif %}
        </td>
        <td class="cal-content">
          {% for reading in day.readings %}
            {% if reading.link %}<a href="{{reading.link}}" class="cal-content-link">{% endif %}
              {{reading.title}}{% if forloop.last == false %};{% endif %}
            {% if reading.link %}</a>{% endif %}
          {% endfor %}
        </td>
        <td class="cal-content">{{day.due}}</td>
      </tr>
    {% endfor %}
  {% endfor %}
  </tbody>
</table>

## Resources

* Readings
  - [J&M III](https://web.stanford.edu/~jurafsky/slp3/): Speech and Language Processing (Dan Jurafsky and James H. Martin)
  - [Eis](https://github.com/jacobeisenstein/gt-nlp-class/blob/master/notes/eisenstein-nlp-notes.pdf): Natural Language Processing (Jacob Eisenstein)
  - Additional readings will be released weekly.
* [Ed discussion board](https://edstem.org/us/courses/86021/discussion/)
<!-- * Zoom link -->
* [Canvas](https://canvas.uw.edu/courses/1828090)
* [Gradescope](https://www.gradescope.com/courses/1116577)

## Assignments/Grading

<!-- 
* Project 1 (sequence classification): 30%
    - We will build a system for automatically classifying song lyrics comments by era. 
    - Specifically, we build machine learning _text classifiers_, including both generative and discriminative models, and explore techniques to improve the models.
* Project 2 (sequence labeling): 30%
    - We focus on sequence labeling with _Hidden Markov Models_ and some simple deep learning based models. 
    - Our task is part-of-speech tagging on English and Norwegian from the Universal Dependencies dataset.
    - We will cover the _Viterbi algorithm_.
* Project 3 (dependency parsing): 30%
    - We will implement a transition-based _dependency parser_.
    - The algorithm would be new and specific to the dependency parsing problem, but the underlying building blocks of the method are still some neural network modules covered in P1 and P2.

-->
* **Project 0 (*Python and Pytorch Tutorial / Review*)**: Optional, Extra 2% Credit.
* **Project 1 (*Text Classification and N-gram language models*)**: 30%
* **Project 2 (*Neural Text Classification and Neural Language Modeling*)***: 30%
* **Project 3 (*Transformers and Natural Language Generation*)***: 30%
* **Quizzes**: 10%
    - Starting from the 3rd week, we will have quizzes on Fridays (unless announced otherwise).
    - There will be 8 quizzes in total.
    - Quizzes will be released 10 minutes in the beginning of the class.
    - 5 best quizzes will be counted into final score. Each quiz will occupy 2% of final score. 
* **Participation**: 6% bonus

*Subject to change based on factors like class performance, compute feasibility, and topics covered during the course.


## Policies

* **Late policy.** Each student will be granted **5 late days** to use over the duration of the quarter. You can use a **maximum of 3 late days** on any one project. Weekends and holidays are also counted as late days. Late submissions are automatically considered as using late days. Using late days will not affect your grade. However, projects submitted late after all late days have been used will receive no credit. Be careful!

* **Academic honesty.** Homework assignments are to be completed individually. Verbal collaboration on homework assignments is acceptable, as well as re-implementation of relevant algorithms from research papers, but everything you turn in must be your own work, and you must note the names of anyone you collaborated with on each problem and cite resources that you used to learn about the problem. The project proposal is to be completed by a team. Suspected violations of academic integrity rules will be handled in accordance with [UW guidelines](https://www.washington.edu/cssc/for-students/overview-of-the-student-conduct-process/) on academic misconduct.

* **On ChatGPT, Copilot, and other AI assistants (adopted from Greg Durrett):** Understanding the capabilities of these systems and their boundaries is a major focus of this class, and there's no better way to do that than by using them!

    - **We strongly encourage you to use ChatGPT to understand concepts in AI and machine learning.** You should see it as a another tool like web search that can supplement understanding of the course material.

    - **You are allowed to use ChatGPT and Copilot for programming assignments.** However, usage of ChatGPT must be limited in the same way as usage of other resources like websites or other students. You should come up with the high-level skeleton of the solution yourself and use these tools primarily as coding assistants.

    - **You are permitted to use ChatGPT for conceptual questions on assignments, but discouraged from doing so.** It will get some of these questions right and some of them wrong. These questions are meant to deepen your understanding of the course content. Heavily relying on ChatGPT for your answers will negatively impact your learning.

  An example of a good question is, "Write a line of Python code to reshape a Pytorch tensor x of [batch size, seqlen, hidden dimension] to be a 2-dimensional tensor with the first two dimensions collapsed." Similar invocation of Copilot will probably be useful as well. An example of a bad question would be to try to feed in a large chunk of the assignment code and copy-paste the problem specification from the assignment PDF. This is also much less likely to be useful, as it might be hard to spot subtle bugs. As a heuristic, it should be possible for you to explain what each line of your code is doing. If you have code in your solution that is only included because ChatGPT told you to put it there, then it is no longer your own work in the same way.

* **Accommodations.** If you have a disability and have an accommodations letter from the Disability Resources office, I encourage you to discuss your accommodations and needs with me as early in the semester as possible. I will work with you to ensure that accommodations are provided as appropriate. If you suspect that you may have a disability and would benefit from accommodations but are not yet registered with the office of Disability Resources for Students, I encourage you to apply [here](https://denali.accessiblelearning.com/Washington/ApplicationStudent.aspx).

## Note to Students

Take care of yourself! As a student, you may experience a range of challenges that can interfere with learning, such as strained relationships, increased anxiety, substance use, feeling down, difficulty concentrating and/or lack of motivation. All of us benefit from support during times of struggle. There are many helpful resources available on campus and an important part of having a healthy life is learning how to ask for help. Asking for support sooner rather than later is almost always helpful. UW services are available, and treatment does work. You can learn more about confidential mental health services available on campus [here](https://www.washington.edu/counseling/). Crisis services are available from the counseling center 24/7 by phone at +1 (866) 743-7732 ([more details here](https://www.washington.edu/counseling/services/crisis/)).
