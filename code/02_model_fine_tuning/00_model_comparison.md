 # Comparison of Summarization Models

 ## Best Fine-Tuned Model
 Based on the analysis summarized below, the best performing summarization model is model 13, using the sshleifer/distilbart-xsum-1-1 with increased maximum lengths for model inputs, 25 epochs of training with an earlystopping callback, and weight decay rate of 0.1. This model recieved the highest rouge f1-scores for Rouge1, RougeL, and RougeLsum, and a comparable Rouge2 f1-score to the second best performing model (model 08). The predicted summaries generated by the processing of test data with this model still do not meet the final goal of the fine-tuned modeling -to a produce accurate and human readable summaries of reference texts- but does produce text including some full sentences, and often obviously related to the context/characters/events described in the associated texts and/or reference summaries. There is further work and development to be done on this model, however it represents progress in the right direction towards achieving desired outcomes.
 
 ## Rouge F1-scores for Test Data
 |Model|Model Checkpoint|Rouge1|Rouge2|RougeL|RougeLsum|
 |---|---|---|---|---|---|
 |02_model (baseline)|summaries constructed with first 3 sentences of text|12.38|1.33|7.33|8.73|
 |03_model|google/mt5-small|8.04|0.0|7.06|7.06|
 |04_model|google/mt5-small|4.18|0.0|4.18|4.18|
 |05_model|facebook/bart-large-xsum|N/A|N/A|N/A|N/A|
 |06_model|sshleifer/distilbart-xsum-1-1|12.66|3.07|7.42|10.04|
 |07_model|sshleifer/distilbart-xsum-1-1|18.51|1.43|9.96|15.66|
 |08_model|sshleifer/distilbart-xsum-1-1|21.51|5.05|11.47|17.92|
 |09_model|sshleifer/distilbart-xsum-1-1|22.22|1.44|14.34|17.92|
 |10_model|google/mt5-small|7.35|0.82|7.35|7.35|
 |11_model|sshleifer/distilbart-xsum-1-1|20.71|2.88|10.71|17.14|
 |12_model|sshleifer/distilbart-xsum-1-1|6.58|1.66|4.12|4.94|
 |13_model|sshleifer/distilbart-xsum-1-1|24.11|5.0|14.18|21.28|
 |14_model|sshleifer/distilbart-xsum-1-1|14.84|0.78|14.06|14.84|

<br>
<br>

## Examples of Model-Generated Summaries
### - Three randomly selected from the predictions of each model -
****************************************************************************************************************************
****************************************************************************************************************************

#### 03_model
"the mountains of the mountains of the mountains of the mountains of the"
<br>
<br>
"Gentlemen, I am joking, and I am joking"
<br>
<br>
N/A

****************************************************************************************************************************

#### 04_model
", which would a few thousand thousands of their"
<br>
<br>
"They would a few believe.
<br>
They would a"
<br>
<br>
"........."

****************************************************************************************************************************

#### 05_model
No summaries generated

****************************************************************************************************************************

#### 06_model
": : : Novel : 2.1 million pounds from Ellen to Linton, and Catherine will not be allowed to leave Linton.
<br>
He tells Ellen that Ellen that he has been struck by Ellen to find her father and daughter.
<br>
She tells her that she will not go to the house, and"
<br>
<br>
"In this chapter, Mr. Lorry arrives at his house."
<br>
<br>
"The Queen tells her of her sister that she does not want her love, but she says she will not go to her housekeeper.
<br>
She tells her that she will take him back into the sea.
<br>
He tells him that she has been imprisoned for life.
<br>
He says that she is"

****************************************************************************************************************************

#### 07_model
"Lady Catherine Collins and Mrs Collins are invited to Mrs. Collins to visit Darcy to the house of Lady Catherine.
<br>
Mrs Collins, and Collins says that Darcy will not go to the party.
<br>
Mr. Collins asks Lady Catherine to Miss Darcy, and Lady Catherine will not be able"
<br>
<br>
": Novel : 4, Huckers and Mrs. Lothrop insists that she will not go to the house, but she wants to go back to her room."
<br>
<br>
"This is one of the world's most famous city in the world, telling them that they would have to go to the forest.
<br>
He tells the story of Virgil, and Virgil tells him that he has been killed."

****************************************************************************************************************************

#### 08_model
"Mr. Collins returns from Wickham and Bingley after their visit to Wickham.
<br>
When they arrive, he finds Wickham, Jane and Wickham discuss the situation.
<br>
Elizabeth is not invited to visit Wickham to visit him.
<br>
He tells Elizabeth that he will not return to Wick"
<br>
<br>
"Jurgis insists that he will not go ahead with his father, who has died aged 66.
<br>
Analysis This causes him to be married to a young man.
<br>
When he returns to his room.
<br>
He is not ready to go back to his house, but he tells him that he would not"
<br>
<br>
": Novel : 2 ???  In this chapter, Hareton and Hareton were killed by a knife attack on a wall near Heathcliff, and he stabbed to death
<br>
in a wall that killed him.
<br>
He is madman, and that he will never be able to kill him, and"

****************************************************************************************************************************

#### 09_model
"In this chapter, Sir Toby, Sir Andrew, delighted by Sir Toby."
<br>
<br>
"Orlando, Orlando, dressed as a fool, and Celia, and Touchstone enter the forest.
<br>
He tells him that he has no chance to marry her and asks him if he wants to marry him.
<br>
She tells him about his future.
<br>
The Duke's daughter, and"
<br>
<br>
"Raskolnikov tells Razumikhin that he has been arrested on suspicion of murder.
<br>
He tells him that he should not be able to find him guilty of murdering him.
<br>
He has been told him he would have to go to the house of the next morning, Razum"

****************************************************************************************************************************

#### 10_model
", a very a very a very a very"
<br>
<br>
"Catherine Catherine, Catherine, Catherine, Catherine, Catherine,"
<br>
<br>
"Dante, Dante, Dante, Dante, Dante, Dante,"

****************************************************************************************************************************

#### 11_model
"In this chapter, Virgil tells the story of the year, and Virgil speaks of his story about his past, telling him that he would have to
<br>
go ahead with his son, who has been living with his father and son, whose son will have to wait until they begin talking to"
<br>
<br>
"The king tells the king that he has been imprisoned in France, and Katherine.
<br>
The king says, as well as his heir to the king.
<br>
He tells him that he will not be able to give up his pardon.
<br>
He says that Katherine has already been given the go-ahead and"
<br>
<br>
"Dante sees Dante and Virgil in the lake, but Dante sees one of the most famous human beings in the forest, and he runs into a lake.
<br>
Virgil speaks to Virgil and his father, so he can leave the house, and then tells the young man to go to Hell."

****************************************************************************************************************************

#### 12_model
"In the Ninth Bolgia, Monte Cristo has become a member of the Crusades."
<br>
<br>
"Viola's daughter, has been taken out of the house of Lady Catherine's house, and she finds her love with her."
<br>
<br>
"Mr. Sowerberry runs into Oliver, and Mr. Bumble, and tries to talk him out of his father."

****************************************************************************************************************************

#### 13_model
"Duke of Albany, dressed as a fool, has become the first woman to win her.
<br>
He tells her that she has been killed.
<br>
Viola's brother, and dismisses them because of her illness.
<br>
They agree to take place in the house of Lady Olivia."
<br>
<br>
"In this chapter, the Count of Monte Cristo's son, Monsieur Villefort, tells him that he wants to marry Maximilian, and the family family to marry her.
<br>
The house of the house, which is one of the most important woman in the world,"
<br>
<br>
"In this chapter, the search for a man who has been working for a few days.
<br>
Analysis This is one of the most important man in the world, as he tries to steal his car from his car, and he finds out that he would have to go back to the ditch the river"

****************************************************************************************************************************

#### 14_model
",,,.,..,, the., the,.
<br>
the, the the the... the.
<br>
the the,, to, the to,.
<br>
to,, and., to the, to., and, the and,.
<br>
and.. to.
<br>
the to"
<br>
<br>
",,,.,..,, the., the,.
<br>
the... the, the the,, to., to,.
<br>
to, the to,, and the, to the, and.
<br>
the the the.
<br>
to.. to the.
<br>
the to the the to"
<br>
<br>
",,,.,, the,..., the.,.
<br>
the, the the.
<br>
the the,, to., to,.
<br>
to, the to,, and the, to the, and.. the.. to.
<br>
the to the.
<br>
to the the to."