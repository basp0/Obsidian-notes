# Stable Matching:
Wizards and Wands have ordered preferences.
### Task 
 Find a stable matching.
### Input
*	n wizards and n wands.
*	Each wizard lists wands in order of preference.
*	Each wand lists wizards in order of preference.

### Output
*	A stable matching of Wizards to Wands.

*Note: Stable matching does not always exist, for example, if $n$ people were to choose among themselves, $n-1$ other people , no stable matching is guaranteed.*
 
### Algorithm for wand selection
#### Initialize
All wizards and wands are initially unmatched.
#####  Algorithm
```
while(some wizard w doesn't have a wand and she/he has not tried every wand)
	v = the wand top most on w's list which has not been tried
	if(v is not chosen already)
		assign(w,v)
	else if(v prefers w over current holder):
		assign(w,v)
	else
		v rejects w // pop(v)
			
``` 

### Observations
* Each wizard tries wands in decreasing order
* Each wizard tries each wand at most once
* Once a wand has a holder, it can not be free, it can only be transfered to another holder. 
### What we need to prove	
*	Algorithm terminates
	 Each wizard tries each wand exactly once $\implies$ At most $n^2$ iterations	
*	Algorithm produces a stable matching

### Claims and Proofs	
$Claim:$ Algorithm termiates with a perfect matching
$Proof:$ 	Suppose wizard $w_i$ does not have a stable matching.
$\implies \exists \ v_i$ (say) without an owner
$\implies$ $w_i$ never tried $v_i$ (contradiction)
$Claim:$  Matching is stable
$Proof:$ Supose that $(w,v)$ is unstable
*	$Case\, I:$ $w$ did not try $v$
		$w$ prefers their current wand $v'$ more than $v$
		$\implies \,(w,v)$ is stable
*	$Case\, II:w$ tried $v$
	$v$ rejected $w$
$\implies$ $v$ prefers current owner more than $w$
$\implies$ $(w,v)$ is stable
   


#CSE222

