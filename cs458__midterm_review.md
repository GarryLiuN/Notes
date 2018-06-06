# CS458 Midterm Review S18

## Module 1 - Introduction

### What is Security

* Confidentiality
  * Access to systems or data is limited to authorized parties
* Integrity
  * When you receive data, you get the **right** data
* Availability
  * The system or data is there when you want it

### What is privacy

* information self-determination
  * You get to **control** information **about you**
* e.g. Personal Information Protection and Electronic Documents Act (PIPEDA)

### Type of Attackers

* Murphy
  * Social engineering
* Amateurs
* Script kiddies
  * unskilled amateur individual who uses script or programs(mostly downloaded from internet) to exploit the system
* Crackers
* Organised crime
* Government "cyberwarriors"
* Terrorists

### Threats

* Interception
  * Unauthorized parties gain access to an asset
* Interruption
  * An asset of the system become lost, unavailable or unusable
* Modification
  * Change existing data
* Fabrication
  * Make up non-existant/fake data 
  * e.g. add someone to payroll who is not employeed by the company

### Methods of Defences

* Prevent:
  * blocking the attack or closing the vulnerability
* Deter:
  * making the attack harder but not impossible
* Deflectby
  * making another target more attractive (or this one less so)
* Detect
  * either as it happens or some time after the fact
* Recover

## Module 2 - Program Security

### Unsecured Programs

* Axiom(Murphy)
  * Programs have bugs
* Corollary
  * Security-relevant programs have security bugs

### Flaws

A flaw is a problem with a program. A **security flaw** is a problem that affects in security in some way (confidentiality, inegrity, availability)

* Fault: undetected
* Failure: detected
  * may lead to ucover the underlying fault

#### Type of flaws

* Intentional/inherent
  * Malicious
    * -- intentionally inserted to attack systems
    * Targeted: victim specified
    * Non-targeted
  * Non-malicious
    * are meant to be in the system
    * may cause failure when used by attacker
    * e.g. backdoors
* Unintentional
  * Buffer overflow
  * Ineger overflow
  * Format string vulnerabilities
  * Imcomplette mediation
  * TOCTTOU errors

#### Heartbleed in OpenSSL (April 2014)

The Heartbleed bug allows the attacker to send malformed(long) messages to the server causing the server to reveal private information.

#### Buffer Overflow

* Target: programs with setuid(superuser) privileges
* Method: Overwrite data past the end of an array(no boundary check); e.g. saved return address
* Variants
  * off-by-one
  * overflow on the heap
  * jump to other part of the program

##### Defences

* Programmer - bound checks
* Stack randomization
* Compiler - Canaries: padding between RET and data and modification will be detected
* Memory: non-executable stack. memory are eith writable or executable but never both
* OS: Virtual Memory

#### Incomplete Mediation

* Mostly web-based applications
* Input from untrusted users
* Request should be *meaningful* and be verified (**meditation**)
* Incompleted Mediation
  * application accepts incorret data
  * may cause buffer overflow and SQL injection

* Client-side meditation
  * done by javascript
  * Problems:
    * Client-side javascript code can be  turned off/modified
    * Communicate with server "manually/directly" without using client-side application

## Module 3 - Operaing System Security