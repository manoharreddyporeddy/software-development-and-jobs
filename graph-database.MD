
cypher
	open standard for querying
	http://www.opencypher.org/

Cypher for
	declarative query langauge
	for working with graph and graph data
		creating data & // writing
		querying data	// reading

	and how to represent bi-directional relationships.

specify the data that we are interested in
	but not how to fetch
focus on domain
	not database

https://www.youtube.com/watch?v=NH6WoJHN4UA
	property graph model used by Neo4j

		nodes			aan, dan				(nouns)
			properties	name, born, twitter		(adjectives)
			labels		:Person, :Car, :Vehicle
				alias	(p:Person)
		relationships	loves, lives with, owns, drives		(verbs)
			properties	since						(adverbs)

Graph pattern matching
	(node)-[:RELATIONSHIP]->(node)
	(node {key:value})-[:RELATIONSHIP*..2]->(node)
		upto 2 relationalships depth


CREATE (:Person {name: "Ann"})		-[:LOVES]->		Create (:Person {name: "Dan"})

// Aan initiated, fbfriend relationship with dan
MATCH (:Person {name: "Ann"})		-[:FB_FRIENDS]->	Create (:Person {name: "Dan"})

// All aan fbfriend relationships
MATCH (:Person {name: "Ann"})		-[:FB_FRIENDS]-		Create (p:Person)


// returns graph (graph data/ visualization)
MATCH
	(a:Address)	<-[:REGISTERED_ADDRESS]->	(o:Officer) -->(e:Entity)
WHERE
	a.address CONTAINS "New York"
RETURN *


// returns aggregation data (tabular data)
MATCH
	(a:Address)	<-[:REGISTERED_ADDRESS]->	(o:Officer) -->(e:Entity)
WHERE
	a.address CONTAINS "New York"
RETURN
	e.jurisdiction_description as j,   COUNT(*) as c
ORDER BY
	c DESC
LIMIT
	10

