# result
My first warehouse

function getSectionTimeList($time_type, $section_code){
    static $cache_list = [];
    $result=[];
    if(empty($cache_list)  ||  !isset($cache_list[$time_type])){
        $cache_list[$time_type] = Db::name('sections_time')->where([
            ['time_type_code', '=', $time_type],
            ['del_tag', '=', '0'],
        ])->column('sections_code,sections_start_time,sections_end_time');
    }

    foreach ($cache_list as  $key=>$value){
        foreach ($value as $k=>$v){
            if ($v['sections_code']==$section_code){
                $result=$v;
            }
        }


    }
    return $result;
}
