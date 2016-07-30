# semlove

This project aims to create and publish a formal model for expressing love relationships. 

## What is love ?

In our initial project research the team turned up several interesting papers from the field of social sciences and psychology.
Fehr & Russel (1991) discuss emotion, attitude and different prototypical kinds of love which could be used as the basis for
a taxonomy of types of love relationship. Regan et al (1998) focus on romantic love and the features of romantic love.

In the semantic web field the only work we are aware of is the [Emotion Ontology of Hastings et al. (2011)](https://github.com/jannahastings/emotion-ontology)
which aims more at describing affective phenomena; and SORON (http://www.bib.uc3m.es/~fcalzada/soron/soron_content/soron) which extends FOAF with properties
for describing social relationships between people.

Our model is based on the work of Sternberg (Sternbery 1986). Sternberg's triangular theory of love describes seven types of love
which consist of all or some of three components - Intimacy, Passion and Commitment. The table below summarises the seven types 
of love and their constituent components:

| Type of Love | Components
+--------------+------------
|  Liking      | Intimacy
|  Infatuation | Passion
|  Empty Love  | Commitment
|  Romantic Love | Intimacy + Passion
|  Companionate Love | Intimacy + Commitment
|  Fatuous Love | Passion + Commitment
|  Consumate Love | Intimacy + Passion + Commitment

## The Model

Our core model of love relationships is time-based. We describe the three components identified by Sternberg as subtypes of "Feeling".
A Feeling is time-bound and is felt by one person for at least one other person. The seven types of love are subtypes of "Love Relation". A Love Relation
is also time-bound and involves at least two people with a mutual set of Feelings for each other.

As both Feelings and Love Relationships are time-bound we consider them to both by types of Event. So our core model looks like this:

                            +-------+
                            | Event |
                            +-------+
                              ʌ   ʌ 
                              |   |
                       +------+   +-------+
                       |                  |
                   +---------+    +---------------+
                   | Feeling |    | Love Relation |
                   +---------+    +---------------+
                        ʌ                 ʌ
           +----------+ |      +--------+ | +---------------+
           | Intimacy |-+      | Liking |-+-| Romantic Love |
           +----------+ |      +--------+ | +---------------+
           +----------+ |   +-----------+ | +-------------------+
           | Passion  |-+   |Infatuation|-+-| Companionate Love |
           +----------+ |   +-----------+ | +-------------------+
         +------------+ |  +------------+ | +--------------+
         | Commitment |-+  | Empty Love |-+-| Fatuous Love |
         +------------+    +------------+ | +--------------+
                                          | +----------------+
                                          +-| Consumate Love |
                                            +----------------+

## Challenges / Open Questions

Perhaps these should migrate to the Issue tracker...

* Challenges from the Open World Assumption. 

  Just because a feeling is not explicitly stated, this does not necessarily mean
  that it does not exist. The OWA implies that we cannot guarantee the absence of a feeling that is not stated. To support 
  more closed statements we would require some form of negation to enable an explicit statement such as "Alice does not feel 
  Passion for Bob"
  
* Disjointness of Love Relationships

  If Alice feels Intimacy and Passion for Bob and Bob feels Intimacy and Passion for Alice, does there exist one love relationship
  (Romantic Love) or three (Romantic Love, Liking and Infatuation). 
  
* Time

  Any inference about love relationships or feelings must take into account time as both Passion and Intimacy must be concurrently
  felt by both parties for each other for a Romantic Love relationship to exist between them. Time is also an element in socially
  constructed relationships (such as partnerships, marriage etc.) and these may also overlap in complex ways with feelings and love relationships. For example, love feelings
  may continue even after a partnership is ended and equally a partnership may continue even after the love relationship that was there
  at the start has ended.
  
* Unrequited Love

  If Alice feels Intimacy and Passion for Bob, but Bob feels only Intimacy for Alice we could infer a Liking relationship 
  based on the mutual Intimacy feelings, but could not establish a Romantic Love relationship as only Alice feels Passion.
  This could be considered an example of unrequited romantic love. Such relationships are a staple of fiction as well as of
  real life, so perhaps there should also be a place for one-sided love relationships.
  
* Upper Ontology

  Our initial work used Dolce as an upper ontology. This still makes sense as Dolce contains many of the core constructs we need
  (in particular events and people). However it might be interesting to also consider mappings to other ontologies. For example,
  how could this work with a combination of FOAF and the W3C Time Ontology?
  
## History

This project was born out of a mini-project at the [12th Semantic Web Summer School](http://sssw.org/2016/]. 
The mini-project was proposed and overseen by Aldo Gangemi and the following is the description given to the
project participants.

    This project is not about the lovers of semantics, but about love itself. Love relationships are the least 
    studied in semantic technologies, despite their super-huge social and economic relevance. You should formalise 
    a non-simplistic understanding of love relationships, e.g. by surveying existing linked data and ontologies to 
    summarise the current state of the art (probably almost null), and by using SSSW techniques: ontology design, 
    knowledge discovery, social web, normative systems, sensor semantics, and your good taste and abilities, to start 
    things off with a reasonable account of love semantics.

The mini-project group was: Kal Ahmed, Kasper Apajalahti, Erwin Flitz, Julia Bosque Gil and Marco Rovera

## References

    * Fehr, B., & Russell, J. A. (1991). The concept of love viewed from a prototype perspective. Journal of Personality and Social Psychology, 60(3), 425.
    * Regan, P. C., Kocan, E. R., & Whitlock, T. (1998). Ain't love grand! A prototype analysis of the concept of romantic love. Journal of Social and Personal Relationships, 15, 411-420
    * Sternberg, Robert J. "A triangular theory of love." Psychological review 93.2 (1986): 119.
