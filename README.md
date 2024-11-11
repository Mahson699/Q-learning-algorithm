# Q-learning-algorithm
Q-learning algorithm costruction for dynamical systems,containing convergance conditions


Q-learning algorithm 
firs of all for implementation of Q-learning on a dynamical system especially in my carier like aerospace vehicles such a quad rotor, helicopres and ..... make you'r vehicle as a function that it's inputs are state,action and outputs was state' , reward . 
 
briefly :    [state' , action , Reward] = quad_rotor( state, action)
 
mind this point in implementation of Q-learning on the dynamical systems, that states there is't similar to
 grid word or other games  to have a quadratic form. cause of time series states  there is have one dimension for example one episode containing 1000 state to  do and simulation ending and then go to the another itration.
but in this case it's neccesary , for each state have a range of action choise.

now i prefer a simple construction for implementing Q-learning on a dynamic vehicles :

you'r code should be devided to 3 part : 
 
1 .  hyper parameter's like learning rate(alpha), discount factor(gamma), probability of acuraing actions(epsilon)
      and you'r initial condition for you'r vehicle or initialize you'r  vehicle parameter's
2.  Q-learning algorithm updating and itrations
3.  giving the results from you'r simulation

now it's time to display the construction : 

