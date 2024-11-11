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
 ------------------------------------------------------------------------------------------
 % implementing Q-learning algorithm on the dynamical system in the Matlab
 % part 1 

epsilon    = 0.9;
discount  = 0.99
alpha       = 0.01;
itration    = 2000;
episode   = 900;
S_0 = ?;     %should be described
action  =  [forward, up, down , back]; % for quad rotor

% there is states should be descrities , for example you want to control pitch chaneel , so it should be discrete also for another chaneels like  % yaw and roll
pitch = -0.5:0.01:+0.5;
Q = zeros( length(pitch) , length(action) ) ; 

-----------------------------------------------------------------------------------------------
% part 2 
action_index     = randi(1,length(action));
state_index      = randi(1,length(action));
for j = 1: itration

S = S_0 ;  % for condition reseting in each itration

for i = 1:episode

% epsilon greedy action selection policy
if rand(0,1) < epsilon
action_index = randi(1,length(action));
act = action(1,action_index);
else
action_index = max(Q(state_index,action_index));
act  = action(1,action_index);
end

 [state,Reward] = quad(S,act);

 state_index_new = find(round(state,2)==pitch);
 if numel(state_index_new)==0
 state_index_new = randi(1,length(state));
 end

 Q(state_index, action_index) = Q(state_index, action_index) + alpha*( R + discount*Q(state_index_new, action_index) - Q(state_index, action_index))
state_index = stete_index_new;

S = state;
end


% Results part
% display the you'r charts

end







