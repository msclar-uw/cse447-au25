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
MWF 3:30-4:20pm, CSE2 G20 (Gates, ground floor)
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

- Please fill out [this feedback form](https://docs.google.com/forms/d/e/1FAIpQLSdFvLJkwO_ZFGGErnI0R9P1bGnZ_QSR1o9LRTtQWcNRD5CiCA/viewform?usp=pp_url) so we know how to improve. Thank you!
  
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
  - [Eis](https://github.com/jacobeisenstein/gt-nlp-class/blob/master/notes/eisenstein-nlp-notes.pdf): Natural Language Processing (Jacob Eisenstein)
  - [J&M III](https://web.stanford.edu/~jurafsky/slp3/ed3book.pdf): Speech and Language Processing (Dan Jurafsky and James H. Martin)
* [Ed discussion board](https://edstem.org/us/courses/66186/discussion/)
<!-- * Zoom link -->
* [Canvas](https://canvas.uw.edu/courses/1746465)
* [Gradescope](https://www.gradescope.com/courses/858262)

## Assignments/Grading

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
* Quizzes: 10%
    - Starting from the 3rd week, we will have quizzes on Wednesdays.
    - There will be 8 quizzes in total.
    - Quizzes will be released 10 minutes in the beginning of the class.
    - 5 best quizzes will be counted into final score. Each quiz will occupy 2% of final score. 

* Participation: 10% bonus

## Policies

* **Late policy.** Each student will be granted **5 late days** to use over the duration of the quarter. You can use a **maximum of 3 late days** on any one project. Weekends and holidays are also counted as late days. Late submissions are automatically considered as using late days. Using late days will not affect your grade. However, projects submitted late after all late days have been used will receive no credit. Be careful!

* **Academic honesty.** Homework assignments are to be completed individually. Verbal collaboration on homework assignments is acceptable, as well as re-implementation of relevant algorithms from research papers, but everything you turn in must be your own work, and you must note the names of anyone you collaborated with on each problem and cite resources that you used to learn about the problem. The project proposal is to be completed by a team. Suspected violations of academic integrity rules will be handled in accordance with [UW guidelines](https://www.washington.edu/cssc/for-students/overview-of-the-student-conduct-process/) on academic misconduct.

* **Accommodations.** If you have a disability and have an accommodations letter from the Disability Resources office, I encourage you to discuss your accommodations and needs with me as early in the semester as possible. I will work with you to ensure that accommodations are provided as appropriate. If you suspect that you may have a disability and would benefit from accommodations but are not yet registered with the office of Disability Resources for Students, I encourage you to apply [here](https://denali.accessiblelearning.com/Washington/ApplicationStudent.aspx).

## Note to Students

Take care of yourself! As a student, you may experience a range of challenges that can interfere with learning, such as strained relationships, increased anxiety, substance use, feeling down, difficulty concentrating and/or lack of motivation. All of us benefit from support during times of struggle. There are many helpful resources available on campus and an important part of having a healthy life is learning how to ask for help. Asking for support sooner rather than later is almost always helpful. UW services are available, and treatment does work. You can learn more about confidential mental health services available on campus [here](https://www.washington.edu/counseling/). Crisis services are available from the counseling center 24/7 by phone at +1 (866) 743-7732 ([more details here](https://www.washington.edu/counseling/services/crisis/)).

## COVID-19 Safety

In light of the COVID-19 pandemic and recent surge in cases due to the Omicron variant, and in accordance with [UW guidelines](https://www.washington.edu/coronavirus/winter2022/), we are implementing the following policies to ensure the safety of our students and instructors to the maximum extent possible:

* **Remote access.** If you are sick or have potentially been exposed to COVID-19, **stay home**! While we encourage everyone to attend class in-person when they are well, there will always be a Zoom meeting for the class and there is no penalty for attending remotely. Office hours are also available both in-person and over Zoom (by appointment).

* **Masking.** When in public, indoor spaces occupied by other people, **you must wear a mask**. This includes class sections and office hours. See more about UW's masking requirements [here](https://www.ehs.washington.edu/covid-19-prevention-and-response/face-covering-requirements). The instructors will abide by the same masking policy.

  For the purposes of this policy, a face covering must fit snugly against the sides of the face and completely cover the nose and mouth. Bandanas and gaiters are not considered face coverings under this policy. Students who do not wear a face mask will be asked to leave the classroom. Repeated failure to wear a face covering may result in being referred to the Student Conduct Office for possible disciplinary action.

  UW has approved a hydration exemption which allows students and instructors to briefly move aside their mask if they are drinking water even in class. This exemption is meant be used only for a brief moment to hydrate, and does not allow talking with one's mask off or having one's mask removed for a prolonged period of time. This exemption does not allow for eating food in classes.
  
* **Social distancing.** Currently, UW does not require social distancing in the classroom or office hours for students who are vaccinated and wearing a mask; it can also make it difficult to navigate and interact in such spaces. We do not mandate social distancing, but ask that if another student asks you to maintain distance from them, that you respect their request.

* **What if you get sick?** See [this FAQ](https://www.washington.edu/coronavirus/faq/) for what to do.

* **What if we get sick?** We will reschedule class, hold it remotely, or bring in a substitute lecturer/facilitator if necessary to prevent exposing students. We will try to give notice as far in advance as possible if an in-person event is moving to be held remotely, but please check your email beforehand to be sure you don't miss anything.
