

   function validBraces($braces) {
       $opened = array();
    $lenStringBraces = strlen($braces);
    if($lenStringBraces <= 0 || $lenStringBraces>= 100){
    return false;
    }  else {
    $braces = str_replace(' ', '', $braces);
    $braces = str_split($braces);
    foreach ($braces as $brace){
        print_r($brace);
    }
                   print "<br>";
    $len = count($braces);
    for($i=0; $i<$len; $i++){
        if ($braces[$i]=='(' || $braces[$i] == '{' || $braces[$i]=='['){
                      $opened [] = $braces[$i];
        }else{
            
         if(($braces[$i] == '}' && array_pop($opened) !== '{')|| ($braces[$i]== ')' && array_pop($opened) !== '(')
                ||($braces[$i] == ']'&& array_pop($opened) !== '[')){
             $last = array_pop($opened);
            return false;

        }
        }
        }
    }
     return !$opened;
   }
    print validBraces("[[]([]{})]]") ? 'true' : 'false';
