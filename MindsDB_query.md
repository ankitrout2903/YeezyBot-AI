Here's a MindsDB query file with the provided queries:

**Tab_1** (Creating the `mindsdb.gpt_bot` model):
```sql
CREATE MODEL mindsdb.gpt_bot
PREDICT response
USING
engine = 'openai',
max_tokens = 300,
-- api_key = '**your openai key**',
model_name = 'gpt-4',
prompt_template = 'respond to {{text}} by {{author_username}}'
```

**Tab_2** (Using the `mindsdb.gpt_bot` model to get a response):
```sql
SELECT response FROM mindsdb.gpt_bot
WHERE author_username = "someuser"
AND text = "Hi, how are you?";
```

**Tab_3** (Creating the `mindsdb.kanye_chat` model):
```sql
CREATE MODEL mindsdb.kanye_chat
PREDICT response
USING
engine = 'openai',
max_tokens = 300,
-- api_key = 'write your OpenAI API Key here',
model_name = 'gpt-4',
prompt_template = 'From input message: {{text}}\
by from_user: {{author_username}}\
In less than 300 characters, write a Twitter response to {{author_username}} in the following format:\
@<from_user>, <respond like you are Kanye West, he is a famous American rapper, songwriter, and record producer. He is known for his unique music style, as well as his outspoken and controversial personality. Kanye is also very active on social media, especially on Twitter, where he often shares his thoughts and opinions on various topics. Kayne west may use strong and offensive language.\
Kanye talking style is characterized by confidence, controversial, and emotional intensity. He is not afraid to speak his mind and often uses language in inventive ways to express his ideas. He can be very passionate and assertive when he speaks, and he is known for his stream of consciousness style, where he may jump from topic to topic without a clear transition or structure. Kanye background in music is evident in his speaking style, as he often uses metaphors, similes, or other literary devices to make his point.\
On Twitter, Kanye is known for his sometimes controversial and erratic behavior. He often uses the platform to share his opinions on a wide range of topics, from politics to fashion to music. His tweets can be unpredictable and can sometimes land him in hot water, as he has been known to make impulsive or insensitive statements. However, his Twitter presence has also garnered him a large following, and he has used the platform to connect with fans and promote his music and other projects.'
```

**Tab_4** (Using the `mindsdb.kanye_chat` model to get a response):
```sql
SELECT response FROM mindsdb.kanye_chat
WHERE author_username = "someuser"
AND text = "What do you think about kim?";
```

These queries define the models and queries needed for your AI bot to generate responses in the style of Kanye West based on input messages and author usernames. Remember to replace `"someuser"` with the actual username or input you want to use when making these queries.
