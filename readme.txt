$ Choose a directory as your local one, and make sure you have set up a Hadoop environment
$ tar -xzvf  Chaofeng_movieRecommender.tar 
$ cd RecommenderSystem
$ hdfs dfs -mkdir /input
$ hdfs dfs -mkdir /MovieTitle
$ hdfs dfs -put input/userRating /input 
$ hdfs dfs -put input/movieTitles.txt /MovieTitle
$ hdfs dfs -rm -r /dataDividedByUser /coOccurrenceMatrix /Multiplication /Recommender
$ cd  src
$ hadoop com.sun.tools.javac.Main *.java
$ jar cf recommender.jar *.class
$ hadoop jar recommender.jar Driver /input /dataDividedByUser /coOccurrenceMatrix /Multiplication /coOccurrenceMatrix/part-r-00000 /input/userRating.txt /MovieTitle/movieTitles.txt /Recommender
#args0: original dataset
#args1: output directory for DividerByUser job
#args2: output directory for coOccurrenceMatrixBuilder job
#args3: output directory for Multiplication job
#args4: file representing co-occurrence matrix
#args5: file representing user rating matrix
#args6: file of movie title 
#args7: output directory for RecommenderListGenerator job, finally the result will be here

