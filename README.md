# odel Learning as a Satisfiability Modulo Theories Problem (DFA-SMT)



# We provide here all expercience provided analysis 'Model Learning as a Satisfiability Modulo Theories Problem'.
**by:** Khalid OUBLAL,

- Google Drive sources [https://drive.google.com/drive/folders/17jRhlsGOv459fzybTg15Al3Qa_VgcLW9?usp=sharing](https://drive.google.com/drive/folders/17jRhlsGOv459fzybTg15Al3Qa_VgcLW9?usp=sharing)
- Documentation [https://smt-dfa.netlify.app/](https://smt-dfa.netlify.app/)
## Experience 1: (Check section 3.1 of the report)

I then compare Z3GI's which is an implementation of Translation-to-SMT in term of performance on a number of systems (algorithms implemented in LearnLib) and Tomte 0.41.I did also same implementation from scratch, baisically to more explore each fonctionality provided on the paper **Model Learning as a Satisfiability Modulo Theories Problem**.

The dataset contains:
- the source code of the Z3GI tool
- the setup built around LearnLib for experiments
- experimental logs
- new implementation of Translation-to-SMT
- various scripts... 

The dataset comprises the folders:

'basic-learning' containing the setup used to run experiments with LearnLib. The setup can 
be imported as a Java project in Eclipse. 
The setup dependencies are:
Java 8 or later
Windows 10 and Boost libraries for Windows (if you want to use the 'Yannakakis.exe' binary)

'Data_output' containing result.csv of experimental results, including those shown in the publication. In particular, this folder includes:
'tomte_experimental_results', an archive containing the experimental data generated by learning scalable systems with Tomte 0.41. As suggested in the paper, 10 experiments were conducted for each system, with three systems being considered, a Login system and FIFO set.

### Login Examples:

```
python DFA-SMT -m experience_1 -a DFA -sc Login -s 1
```

### FIFO Examples:

Please run at your shell (anaconda/linx shell) this commande:

```
python DFA-SMT -m experience_1 -a DFA -sc Login -s 1

```
This mean that you are going to use Translation-to-SMT approach (the main method of our report) et ensuit `experience_1` ppour signifier l'emplacement des script liée à cette approach, et finalement l'argument `Login` ou `FIFOSet` pour indiquer le type de sytème à entrainer. Finaly `1` indecate number of users to use system of Login,the same for FIFO 1 is number of set inputs. We did a clear comment on this in section (3.1) in our report.

**Example**
The output of this `python DFA-SMT -m experience_1 -a DFA -sc Login -s 1` is:

```
CE:  (['login'], False)
CE:  (['logout', 'logout', 'logout', 'login'], False)
CE:  (['register', 'logout', 'login'], False)
CE:  (['logout', 'logout'], False)
CE:  (['register', 'register', 'logout', 'logout', 'logout'], False)
CE:  (['logout', 'register'], False)
CE:  (['register', 'logout', 'register', 'register', 'register', 'login'], False)
CE:  (['register', 'login', 'register', 'login', 'logout', 'logout'], False)
CE:  (['logout', 'register', 'logout'], False)
CE:  (['login', 'logout'], False)
CE:  (['logout', 'logout', 'logout', 'logout', 'login'], False)
CE:  (['login', 'logout', 'register', 'register', 'register', 'login', 'register'], False)
CE:  (['register', 'login', 'logout', 'logout', 'register', 'login', 'logout'], False)
CE:  (['logout', 'logout', 'logout', 'register'], False)
CE:  (['register', 'logout'], False)
CE:  (['register', 'login', 'register'], False)
CE:  (['register', 'register', 'logout'], False)
CE:  (['register', 'register', 'register', 'register', 'register', 'login'], False)
CE:  (['register', 'register', 'login', 'register'], False)
CE:  (['logout', 'register', 'logout', 'register', 'logout', 'logout'], False)
CE:  (['login', 'login', 'register'], False)
CE:  (['login', 'register'], False)
CE:  (['logout', 'login', 'login', 'logout', 'login'], False)
CE:  (['logout', 'logout', 'logout', 'login', 'logout', 'login'], False)
CE:  (['register', 'register', 'login', 'register', 'register'], False)
CE:  (['register', 'register', 'logout', 'login', 'login', 'register', 'logout'], False)
CE:  (['register', 'login'], True)
CE:  (['login', 'logout', 'register', 'register', 'logout', 'login'], False)
CE:  (['register', 'login', 'login', 'login', 'register', 'login'], False)
CE:  (['login', 'logout', 'logout', 'register', 'login'], False)
CE:  (['register', 'logout', 'logout', 'register', 'login'], False)
CE:  (['register', 'login', 'logout', 'logout', 'login'], False)
CE:  (['register', 'login', 'logout', 'logout', 'login', 'login', 'login'], False)
CE:  (['register', 'login', 'login', 'register', 'login'], False)
CE:  (['login', 'logout', 'logout', 'register', 'login', 'login'], False)
CE:  (['register', 'register'], False)
CE:  (['login', 'login'], False)
CE:  (['register', 'login', 'register', 'register', 'login'], False)
CE:  (['register', 'register', 'register', 'logout', 'login'], False)
CE:  (['register', 'logout', 'register', 'login', 'register', 'login'], False)
CE:  (['register', 'login', 'login', 'login'], False)
CE:  (['register', 'login', 'logout', 'logout', 'logout'], False)
CE:  (['logout'], False)
CE:  (['register', 'login', 'register', 'login', 'register', 'login'], False)
Learned model
{'q0': True, 'q1': False, 'q2': True, 'q3': True}
acc_seq(q0) = 
acc_seq(q1) = q0 login -> q1
acc_seq(q2) = q0 register -> q2
acc_seq(q3) = q0 register -> q2 , q2 login -> q3
q0
register -> q2
login -> q1
logout -> q1
q1
register -> q1
login -> q1
logout -> q1
q2
register -> q1
login -> q3
logout -> q1
q3
register -> q1
login -> q1
logout -> q2

With stats
Tests until last hyp: 0 
Inputs until last hyp: 0 
Hypotheses used in learning: 45 
Learning time for each model: [76, 62, 33, 39, 41, 38, 77, 52, 54, 59, 55, 52, 63, 63, 62, 65, 61, 116, 77, 78, 79, 78, 82, 81, 81, 85, 86, 86, 92, 87, 89, 92, 95, 92, 94, 96, 94, 97, 96, 97, 98, 103, 102, 102, 101] 
Total learning time: 3508 
-------------------
result is saved on resutl.csv -------------------
--------- ok  PLEASE CHECK DATA OUTPUT FOLDER--------
```
As we see here, the model description it can be split into 4 sections.

- the first section indicates acceptance/rejection of each state
the second section indicates access sequences to each state, in later versions, this section may be ommitted
- the third section describes transitions of the learned model
- the four section describes an operation was achieved to save the output statistics.

The output of each experiment is placed in a separate directory in the folder.


## Experience 2: (Check section 3.2 of the report)

In order to proceed with the study case, you must first make sure you have java on your computer, a C++ compiler (like Eclipse). The data we have tested are in the Sample folder.

The SMT_new.py file is the new implementation of the translation-to-SMT method by considering not the map function but rather the use of variable x in the whole F family (See our report section, 2.3).

Then, we did not succeed in providing a single file ( due to the time constraints) that allows us to do all the tests and record them, but rather to test each method separately. 

The different results in terms of CPU performance (time execution).
A relevant analysis was given to these results in section (3.2) of our report.
