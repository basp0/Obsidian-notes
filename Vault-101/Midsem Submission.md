A. List all ‘Audio’ albums released in 2020.
$Solution$
#### $\prod_{\,title\,}(\sigma_{ type\ =\ "Audio"\, and\,release\_date\,\geq\,01-01-2020\,and\,release\_date\,\leq\,31-12-2020 }(Approved\_album\bowtie_{Approved\_album.approved\_album\_id=Album.album\_id} Album ))$
 B. List all participants who have submitted both Audio and Video files. (2) 
#### $\prod_{first\_name,last\_name}(Candidate\bowtie\sigma_{Entry.type\,=\,"audio"\,and\,Entry\_copy.type\,=\,"video"\,and\,Entry.candidate\_id = Entry\_copy.candidate\_id}(Entry \,X\, \rho_{Entry\_copy}(Entry)))$

C. List all members who have been the member of more than one group (3) 
#### $\prod_{first\_name,last\_name}(Candidate \bowtie_{Candidate.candidate\_id = belongs\_to.member\_id}$ $\sigma_{belongs\_to.member\_id=belongs\_to\_copy.member\_id \, and \, belongs\_to.group\_id!=belongs\_to\_copy.group\_id}(belongs\_to\,X\,\rho_{belongs\_to\_copy}(belongs\_to)))$
D. List all members of ‘Pop’ music group who are not part of any other music group.

#### $\prod_{first\_name,last\_name} (Candidate\bowtie(\sigma_{genre = "pop" }( Belongs\_to\,\bowtie\,Group)-\sigma_{genre != "pop" }( Belongs\_to\,\bowtie\,Group)))$
(3) E. List all distributors who sold all types of albums 

### $\prod_{name}(Distributor \bowtie(\sigma_{r1.distributor\_token=r2.distributor\_token\,  and\, r1.type!=r2.type }(\rho_{r1}(released\_to \bowtie Album) \,X\,\rho_{r2}(released\_to \bowtie Album))))$

# Q5
A.
### SELECT * FROM 

B.
### SELECT 
