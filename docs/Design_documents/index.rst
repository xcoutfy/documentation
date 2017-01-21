Design Documents
===========================



.. graphviz::

   digraph {
      "From" -> "To";
   }



.. uml::

   @startuml
   Alice -> Bob: Hi!
   Alice <- Bob: How are you?
   @enduml


#. Architecture
#. UML diagrams
    * Use Cases
    * Sequence Diagrams
    * Class Diagram
#. Code Organisation
#. Requisites and Growth analysis
#. Backup Policy and disaster recovery




.. uml::

  @startuml
  object Object01
  object Object02
  object Object03
  object Object04
  object Object05
  object Object06
  object Object07
  object Object08
  Object01 <|-- Object02
  Object03 *-- Object04
  Object05 o-- "4" Object06
  Object07 .. Object08 : some labels
  @enduml

  .. uml::

   @startuml
   Alice -> Bob: Hi!
   Alice <- Bob: How are you?
   @enduml
