# Comp23412 Software Engineering 2 

## Week 1 : Model-View-Controller



### MVC components 

#### Curl Command

- -X POST: this tells curl we want to perform a POST. By default it uses GET.
- -H "Accept: application/json": this sets the Accept header, as explained above.
- -H "Content-Type: application/json": this sets the Content-Type header. To add a new greeting we need to tell the server what that greeting is, and what format we are sending it in.
- -d '{ "template": "Howdy, %s" }': this is the data that we are sending to the server to create our new greeting. It's in json format, as we specified with the Content-Type header. Note the use of different types of quotes: we need to use '' around the data, because json expects "" to be used to quote the keys and values that make up the data.
- http://Rob:Haines@localhost:8080/api/greetings: this is the address to which we are POSTing our data to create the new greeting. Remember that we need to authenticate to create a new greeting, so that information has been embedded into the URI in the standard way. This isn't necessarily the most secure way of doing that, but it's fine for these purposes.









## Week 2：Designing the user interface  

### 1.From requirement to design 

Different fidelity levels: **Sketches** , **wireframe** , **mockups** , **prototypes** 

不同的保真度等级：草图，线框、模拟图。
原型

![1676076219425](C:\Users\38673\OneDrive\文档\WeChat Files\wxid_la8i463jklrb12\FileStorage\Temp\1676076219425.png)

![1676076235883](C:\Users\38673\OneDrive\文档\WeChat Files\wxid_la8i463jklrb12\FileStorage\Temp\1676076235883.png)

![1676076248228](C:\Users\38673\OneDrive\文档\WeChat Files\wxid_la8i463jklrb12\FileStorage\Temp\1676076248228.png)



Why mockups 

- Stimulate a dialogue with the customer
- Showing different choices 
- Exchange of ideas 

Save time 

- Prevent misunderstandings
- remove bugs early on 

Tips

- Extract the tasks from requirements
- Follow a top-bottom approach



### 2.Guidelines for user interface design 

Ben Shneiderman's 8 golden rules 

- Strive for consistency  开发过程中保持的一致性

  **Q:How can the consistency guideline be used to take advantage of the user?**

  A: Since consistency boosts learnability we may unintentionally click on a button we don't want to 

- Seek univeral usability 

  - Users 
    - Ability 
    - Age
    - Skills
  - Devices 
    - Assistive technology 
    - Wearable>Mobile>Desktop>Large display 
  - Situation 

  ​       On the move 

  ​        Weather

- Offer informative feedback 

  -  Say what happened and why 
  - Suggest a next step 
  - Find the right tone

  ![1676156132621](C:\Users\38673\OneDrive\文档\WeChat Files\wxid_la8i463jklrb12\FileStorage\Temp\1676156132621.png)

  Which dialogues offer informative feedback ?

  Bing and Twitter 

- Design dialogues that bring closure

- Prevent errors 

  Q: how would you improve further this user interfaces?

  A: Preventing users from selecting dates in the past

![1676156029751](C:\Users\38673\OneDrive\文档\WeChat Files\wxid_la8i463jklrb12\FileStorage\Temp\1676156029751.png)

- Permit easy reversal of actions 

​    ![1676156273658](C:\Users\38673\OneDrive\文档\WeChat Files\wxid_la8i463jklrb12\FileStorage\Temp\1676156273658.png)

- Keep users in control 

![1676156320235](C:\Users\38673\OneDrive\文档\WeChat Files\wxid_la8i463jklrb12\FileStorage\Temp\1676156320235.png)

- Reducing short-term memory load 

![1676156513040](C:\Users\38673\OneDrive\文档\WeChat Files\wxid_la8i463jklrb12\FileStorage\Temp\1676156513040.png)

Q: How to fix these ?

A: 

![1676156542394](C:\Users\38673\OneDrive\文档\WeChat Files\wxid_la8i463jklrb12\FileStorage\Temp\1676156542394.png)