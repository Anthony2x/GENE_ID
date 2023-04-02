# GENE_ID
<!DOCTYPE html>
<html>
    <style>

        body{
            background-color:rgb(87, 76, 76);
        }

        header{
         background-color:rgb(84, 146, 117);;
         border-radius: 30px;
         border: 3px solid white;
        }
        h1{
         color: white;
         text-align: center;
         cursor: pointer;
        }
        .cript{
            background: url(dna-gif.gif);
            background-size: 300px;
            border: 4px solid white;
            border-radius: 30px
        }
        .late{
            position:auto;
            top: 30%;
            background: url(rna2-gif.gif);
            background-size: 300px;
            border: 4px solid white;
            border-radius: 30px;

        }
        .speed_motion{
            background-color:black;
            padding:10px;
            border-radius: 30px;
            border: 3px solid white;
        }
        p{
            color: white;
        }
        .tes{
            border:3px solid black;
            border-radius: 15px;
        }
        button{
            cursor: pointer;
            margin-top: 10px;
            padding:5px;
            border-radius: 30px;
            background-color: blue;
            color: cornsilk;
            border: 3px solid white;
        }
        .trn-1{
            background-color: white;
        }
        .tein{
            background: url(protein-gif.gif);
            background-size: 300px;
            border: 4px solid white;
            border-radius: 30px;
        }
        .exp-lain{
            background-color: black;
            position: absolute;
            left:40%;
            top:40%;
            padding: 20px;
            border-radius: 30px;
            visibility: hidden;
            border: 3px solid white;
        }
        .exp-lain.show{
            visibility: visible;
        }
        .err-or{
            color:white;
            background-color: red;
            padding:20px;
            width: 600;
            position: absolute;
            border-radius: 30px;
        }
       
        
       

    </style>
    <body>
        <header>
            <h1 onclick='express()'>bio: Gene Expression(click)</h1>
            
        </header>
        <p></p>
        
        <div class = 'cript'>
            <p class='speed_motion' onclick = 'motion()'>TRANSCRIPTION</p><br>
            <textarea cols ="60" rows ="5" class = "tes" id = "txt_1" placeholder="Type for transcription....."></textarea><br>
            <button onclick = "dna()">Transcribe DNA</button><br>
            <P id ="new"></P>
            <div class = "trn-1" id ="te_2">

            </div>
            
        </div>
        <p></p>

        <div class = 'late'>
            <p class='speed_motion' onclick = 'motion()'>TRANSLATION</p><br>
            <textarea cols ="60" rows ="5" class = "tes" id = "txt_2" placeholder="Type for translation....."></textarea><br>
            <button onclick = "rna()">Translate RNA</button><br>
            <P id ="new"></P>
            <div class = "trn-1" id ="te_3">

            </div>
            
        </div>
        <p></p>

        <div class = 'tein'>
            <p class='speed_motion' onclick = 'motion()'>PROTEIN</p><br>
            <textarea cols ="60" rows ="5" class = "tes" id = "txt_3" placeholder="Type to get amino-acids....."></textarea><br>
            <button onclick = "tna()">Get Protein</button><br>
            <P id ="new"></P>
            <div class = "trn-1" id ="te_4">

            </div>
            
        </div>

        <div class="exp-lain" id="exp_lain">
            <p>For DNA </p>
            <p> A (Adenine(purine)) converts to T (thymine(pyrimidine))-----Vice Versa </p>
            <p> G (Guanine(purine)) converts to C (Cytosine(pyrimidine)) ----- Vice Versa </p>

            <p>For RNA </p>
            <p> A (Adenine(purine)) converts to U (Uracil(pyrimidine))-----Vice Versa </p>
            <p> G (Guanine(purine)) converts to C (Cytosine(pyrimidine)) ----- Vice Versa </p>
            <p> T (Thymine(pyrimidine)) converts to A (Adenine(purine))</p>

            <p>For Protein: the translated RNA creates the protein</p>
 
        </div>

        <div class="err-rr" id="error"></div>
        
        <script>
            function explaination(){
                var explain = document.getElementById("exp_lain")
                explain.classList.toggle("show")
            }


            function dna(){
                explaination()
                var tra = document.getElementById("txt_1").value;
                var ans_2 = document.getElementById("te_2")
                new_gene = ""
                
                for( i of tra){
                    if (i == 'A'){
                        new_gene += 'T'
                    };
                    
                    if(i == 'T'){
                        new_gene += 'A'
                    }
                    if(i == 'C'){
                        new_gene += 'G'
                    }
                    if(i == 'G'){
                        new_gene+= 'C'
                    }
                    else{
                        
                    }
                ans_2.innerHTML = new_gene
                } 
            }
             
            
            function rna(){
                explaination()
                var tra_2 = document.getElementById("txt_2").value;
                var ans_3 = document.getElementById("te_3")
                new_gene_2 = ""
                
                for( i of tra_2){
                    if (i == 'A'){
                        new_gene_2 += 'U'
                    }
                    if(i == 'T'){
                        new_gene_2 += 'A'
                    }
                    if(i == 'C'){
                        new_gene_2 += 'G'
                    }
                    if(i == 'G'){
                        new_gene_2+= 'C'
                    }
                    if(i == 'U'){
                        new_gene_2+= 'A'
                    }
                    
                    else{
                        
                    }
                ans_3.innerHTML = new_gene_2
                }
            }

            function tna(){
                explaination()
                var tra_3 = document.getElementById("txt_3").value;
                var ans_4 = document.getElementById("te_4")
                var list_gene =[]
                var protein = []
                var new_gene_3 = ""

                for(i of tra_3){
                    new_gene_3 += i
                    if(new_gene_3.length == 3){
                        list_gene.push(new_gene_3)
                        new_gene_3 = ""
                    }
                }
                console.log(list_gene)

                for(k of list_gene){
                    if (k.includes('UUU') || k.includes('UUC')){
                        protein.push('Phenylalanine')
                    }
                    
                    if(k.includes('UUA') ||k.includes('UUG') || k.includes('CUU') || k.includes('CUC')||k.includes('CUA')||k.includes('CUG')){
                        protein.push('Leucine')
                    }
                    if(k.includes('AUU') ||k.includes('AUC') || k.includes('AUA')){
                        protein.push('Isoleucine')
                    }
                    if (k.includes('AUG')){
                        protein.push('Methionine(start)')
                    }
                    if(k.includes('GUU') ||k.includes('GUC') || k.includes('GUA') || k.includes('GUG')){
                        protein.push('Valine')
                    }
                    if(k.includes('UCU') ||k.includes('UCC') || k.includes('UCA') || k.includes('UCG') || k.includes('AGU') || k.includes('AGC')){
                        protein.push('Serine')
                    }
                    if(k.includes('CCU') ||k.includes('CCC') || k.includes('CCA') || k.includes('CCG')){
                        protein.push('Proline')
                    }
                    if(k.includes('ACU') ||k.includes('ACC') || k.includes('ACA') || k.includes('ACG')){
                        protein.push('Threonine')
                    }
                    if(k.includes('GCU') ||k.includes('GCC') || k.includes('GCA') || k.includes('GCG')){
                        protein.push('Alanine')
                    }
                    if(k.includes('UAU') ||k.includes('UAC')){
                        protein.push('Tyrosine')
                    }
                    if(k.includes('UAA') ||k.includes('UAG') || k.includes('UGA')){
                        protein.push('Stop')
                    }
                    if(k.includes('CAU') ||k.includes('CAC')){
                        protein.push('Histidine')
                    }
                    if(k.includes('CAA') ||k.includes('CAG')){
                        protein.push('Glutamine')
                    }
                    if(k.includes('AAU') ||k.includes('AAC')){
                        protein.push('Asparagine')
                    }
                    if(k.includes('AAA') ||k.includes('AAG')){
                        protein.push('Lysine')
                    }

                    if(k.includes('GAU') ||k.includes('GAC')){
                        protein.push('Aspartic Acid')
                    }
                    if(k.includes('GAA') ||k.includes('GAG')){
                        protein.push('Glumatic Acid')
                    }
                    if(k.includes('UGU') ||k.includes('UGC')){
                        protein.push('Cysteine')
                    }
                    if(k.includes('UGG')){
                        protein.push('Tryptophan')
                    }
                    if(k.includes('CGU') ||k.includes('CGC') || k.includes('CGA') || k.includes('CGG')||k.includes('AGA')||k.includes('AGG')){
                        protein.push('Arginine')
                    }
                    if(k.includes('GGU') ||k.includes('GGC') || k.includes('GGA') || k.includes('GGG')){
                        protein.push('Glycine')
                    }
                    
                       
                }
                
                ans_4.innerHTML = protein
            }
//EXPRESS ALL GENES
            function express(){

                explaination()
                var tra = document.getElementById("txt_1").value;
                var ans_2 = document.getElementById("te_2")
                new_gene = ""
                
                for( i of tra){
                    if (i == 'A'){
                        new_gene += 'T'
                    };
                    
                    if(i == 'T'){
                        new_gene += 'A'
                    }
                    if(i == 'C'){
                        new_gene += 'G'
                    }
                    if(i == 'G'){
                        new_gene+= 'C'
                    }
                    else{
                        
                    }
                ans_2.innerHTML = new_gene
                } 
                var tra_2 = document.getElementById("txt_2").value = new_gene;
                var ans_3 = document.getElementById("te_3")
                new_gene_2 = ""
                
                for( i of tra_2){
                    if (i == 'A'){
                        new_gene_2 += 'U'
                    }
                    if(i == 'T'){
                        new_gene_2 += 'A'
                    }
                    if(i == 'C'){
                        new_gene_2 += 'G'
                    }
                    if(i == 'G'){
                        new_gene_2+= 'C'
                    }
                    if(i == 'U'){
                        new_gene_2+= 'A'
                    }
                    
                    else{
                        
                    }
                ans_3.innerHTML = new_gene_2
                }
                var tra_3 = document.getElementById("txt_3").value = new_gene_2;
                var ans_4 = document.getElementById("te_4")
                var list_gene =[]
                var protein = []
                var new_gene_3 = ""

                for(i of tra_3){
                    new_gene_3 += i
                    if(new_gene_3.length == 3){
                        list_gene.push(new_gene_3)
                        new_gene_3 = ""
                    }
                }
                console.log(list_gene)

                for(k of list_gene){
                    if (k.includes('UUU') || k.includes('UUC')){
                        protein.push('Phenylalanine')
                    }
                    
                    if(k.includes('UUA') ||k.includes('UUG') || k.includes('CUU') || k.includes('CUC')||k.includes('CUA')||k.includes('CUG')){
                        protein.push('Leucine')
                    }
                    if(k.includes('AUU') ||k.includes('AUC') || k.includes('AUA')){
                        protein.push('Isoleucine')
                    }
                    if (k.includes('AUG')){
                        protein.push('Methionine(start)')
                    }
                    if(k.includes('GUU') ||k.includes('GUC') || k.includes('GUA') || k.includes('GUG')){
                        protein.push('Valine')
                    }
                    if(k.includes('UCU') ||k.includes('UCC') || k.includes('UCA') || k.includes('UCG') || k.includes('AGU') || k.includes('AGC')){
                        protein.push('Serine')
                    }
                    if(k.includes('CCU') ||k.includes('CCC') || k.includes('CCA') || k.includes('CCG')){
                        protein.push('Proline')
                    }
                    if(k.includes('ACU') ||k.includes('ACC') || k.includes('ACA') || k.includes('ACG')){
                        protein.push('Threonine')
                    }
                    if(k.includes('GCU') ||k.includes('GCC') || k.includes('GCA') || k.includes('GCG')){
                        protein.push('Alanine')
                    }
                    if(k.includes('UAU') ||k.includes('UAC')){
                        protein.push('Tyrosine')
                    }
                    if(k.includes('UAA') ||k.includes('UAG') || k.includes('UGA')){
                        protein.push('Stop')
                    }
                    if(k.includes('CAU') ||k.includes('CAC')){
                        protein.push('Histidine')
                    }
                    if(k.includes('CAA') ||k.includes('CAG')){
                        protein.push('Glutamine')
                    }
                    if(k.includes('AAU') ||k.includes('AAC')){
                        protein.push('Asparagine')
                    }
                    if(k.includes('AAA') ||k.includes('AAG')){
                        protein.push('Lysine')
                    }

                    if(k.includes('GAU') ||k.includes('GAC')){
                        protein.push('Aspartic Acid')
                    }
                    if(k.includes('GAA') ||k.includes('GAG')){
                        protein.push('Glumatic Acid')
                    }
                    if(k.includes('UGU') ||k.includes('UGC')){
                        protein.push('Cysteine')
                    }
                    if(k.includes('UGG')){
                        protein.push('Tryptophan')
                    }
                    if(k.includes('CGU') ||k.includes('CGC') || k.includes('CGA') || k.includes('CGG')||k.includes('AGA')||k.includes('AGG')){
                        protein.push('Arginine')
                    }
                    if(k.includes('GGU') ||k.includes('GGC') || k.includes('GGA') || k.includes('GGG')){
                        protein.push('Glycine')
                    }
                    ans_4.innerHTML = protein
                       
                }
            

// detecting error
            var tra_J = document.getElementById("txt_1").value;
            var get_error = document.getElementById("error")
            var create_p = document.createElement("p");
            create_p.classList.add("err-or")
            var len = tra_J.length;
            var text_error = "Mutation detected(insertion or deletion), potential cancer or sickle cell imminent"
            if(len % 3 == 0){
                console.log('ok')
            }
            else{
               create_p.innerHTML = text_error
               get_error.append(create_p)
               console.log('error, mutation detected')
            }
            console.log(len)

        }



            
               

            
        </script>
    </body>
</html>
