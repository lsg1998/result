# result
My first warehouse



    foreach ($cache_list as  $key=>$value){
        foreach ($value as $k=>$v){
            if ($v['sections_code']==$section_code){
                $result=$v;
            }
        }


    }
    return $result;
}
