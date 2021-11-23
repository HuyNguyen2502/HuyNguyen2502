<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Yêu Tố My</title>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css"
        integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">
</head>

<body>
     
    <p class="test d-none">
    1. Martin Luther King devoted his life to the ____ of voting right for black people.
A. effort 		B. realization 		C. achievement 		D. performance 
2. His father used to be a ____ professor at the university. Many students worshipped him..
A. distinct 		B. distinctive 		C. distinguishing 		D. distinguished 
3. Mark Zuckerberg's enormous success has taken a lot of hardwork and ____.
A. indifference 	B. dedication 		C. loyalty 		D. reputation 
4. I can't believe she didn't do anything for the company. I will ____ and be in charge. 
A. take over		B. take on		C. take up		D. take in 
5. During the Medieval period, people were made public ____ of being witches. 
A. complaint 		B. criminal		C. trouble		D. accusation 
6. That disable boy's victory in the race set the ____ example to all students in the school. 
A. finest 		B. first-class 		C. rarest		D. most convenient 
7. A ____ once said “It is a sweet and honourable thing to die for your country.” 
A. patriotism 		B. patriotic		C. patriot		D. patrol
8. He is ____-influenced by his father and grandfather. His behaviors and decisions are exactly the same. 
A. mightily 		B. strongly 		C. terribly		D. weakly 
9. IPhone 7 is the latest ____ in the field of smartphone design of Apple. 
A. creator 		B. create		C. creativity 		D. creation 
10. Einstein ____ a great impact on modern physics. 
A. feels 		B. does 		C. a			D. has 












</p>
    <div class="button">
	    <h7 class="font-600 d-block"><i>Bấm vào mấy cái nút chữ cái</i></h7>
    </div>
    
    <ul class="listTest">
    </ul>
    <style>
        .listTest {
            margin-top: 0;
        }
	    .font-600{
		    font-weight: 600;
		    color: white;
		    display: block;
	    }
        .button {
            position: sticky;
            position: -webkit-sticky;
            top: 0;
            right: 0;
            left: 0;
            background-color: dodgerblue;
        }

        .btnChar {
            margin: 5px;
            padding: 5px;
            width: 40px;
            height: 40px;
        }
    </style>
    <script>
        const obj = {
            A: [],
            B: [],
            C: [],
            D: [],
            E: [],
            H: [],
            K: [],
            L: [],
            M: [],
            N: [],
            O: [],
            P: [],
            Q: [],
            S: [],
            T: [],
            V: [],
            Y: []
        }
        const test = document.querySelector(".test")
        const textTest = test.innerHTML
        const textArray = textTest.split(/Câu \d+[:.] /)
        textArray.sort((a, b) => a.localeCompare(b))
        const list = document.querySelector(".listTest")
        textArray.forEach((item, index) => {
            obj[removeAccents(item[0].toUpperCase())]?.push(item)
            list.innerHTML += `
            <li>
                <h5>
                    ${item.slice(0, item.search(/[abcdABCD][.]/))}
                </h5>
                <p>${item.slice(item.search(/[abcdABCD][.]/), item.length)}</p>
            </li>`
        })
        function removeAccents(str) {
            return str.normalize('NFD')
                .replace(/[\u0300-\u036f]/g, '')
                .replace(/đ/g, 'd').replace(/Đ/g, 'D');
        }
        const btn = document.querySelector(".button")
        Object.keys(obj).map((item) => {
            if (obj[item].length > 0){
                btn.innerHTML += `<button class="btnChar" onclick="search(this)">${item}</button>`
            }
        })
        function search(ed) {
            window.scrollTo(0,0)
            obj[ed.innerText].forEach((item, index) => {
		    
		if(item !==""){
			if (index === 0) {
                    		list.innerHTML = `
                        		<li class="question">
						<p class="text-decoration-underline text-primary" onclick="hiddenQuestion('${ed.innerText}',${index},event)">Ẩn</p>
                           			 <h5>
                               			 ${item.slice(0, item.search(/[abcdABCD][.]/))}
                           			 </h5>
                            			<p>${item.slice(item.search(/[abcdABCD][.]/), item.length)}</p>
                        		</li>`
                	} else {
                    		list.innerHTML += `
                        		<li class="question">
						<p class="text-decoration-underline text-primary"  onclick="hiddenQuestion('${ed.innerText}',${index},event)">Ẩn</p>
                           			 <h5>
                                		${item.slice(0, item.search(/[abcdABCD][.]/))}
                            			</h5>
                           			 <p>${item.slice(item.search(/[abcdABCD][.]/), item.length)}</p>
                        		</li>`
               		 }
		}else{
			if (index === 0){
				list.innerHTML = ``
			}
		}
                
            })
        }
	    function hiddenQuestion(char,indexchar,e){
		    e.target.parentElement.classList.add("d-none")
		    obj[char][indexchar]=""
		    
	    }
    </script>




    <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js"
        integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN"
        crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js"
        integrity="sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q"
        crossorigin="anonymous"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js"
        integrity="sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl"
        crossorigin="anonymous"></script>
</body>

</html>
