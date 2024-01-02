```php
function Wo_GetFreeReferrers($user_id = 0)
{
    global $sqlConnect, $wo;

    if ($wo['loggedin'] == false) {
        return false;
    }

    if (empty($user_id)) {
        $user_id = Wo_Secure($wo['user']['user_id']);
    } else {
        $user_id = Wo_Secure($user_id);
    }

    $data = array();
    $count = 0;

    $query_one = "SELECT * FROM " . T_USERS . " WHERE `referrer` = '{$user_id}'";
    $sql_query_one = mysqli_query($sqlConnect, $query_one);

    if (mysqli_num_rows($sql_query_one)) {
        while ($fetched_data = mysqli_fetch_assoc($sql_query_one)) {
            if ($fetched_data['is_pro'] == '0') {
                $count++;
            }

            $query_two = "SELECT * FROM " . T_USERS . " WHERE `referrer` = '{$fetched_data['user_id']}'";
            $sql_query_two = mysqli_query($sqlConnect, $query_two);

            if (mysqli_num_rows($sql_query_two)) {
                while ($fetched_datas = mysqli_fetch_assoc($sql_query_two)) {
                    if ($fetched_datas['is_pro'] == '0') {
                        $count++;
                    }

                    $query_three = "SELECT * FROM " . T_USERS . " WHERE `referrer` = '{$fetched_datas['user_id']}'";
                    $sql_query_three = mysqli_query($sqlConnect, $query_three);

                    if (mysqli_num_rows($sql_query_three)) {
                        while ($fetched_datass = mysqli_fetch_assoc($sql_query_three)) {
                            if ($fetched_datass['is_pro'] == '0') {
                                $count++;
                            }
                            $query_four = "SELECT * FROM " . T_USERS . " WHERE `referrer` = '{$fetched_datass['user_id']}'";
                            $sql_query_four = mysqli_query($sqlConnect, $query_four);

                            if (mysqli_num_rows($sql_query_four)) {
                                while ($fetched_datasss = mysqli_fetch_assoc($sql_query_four)) {
                                    if ($fetched_datasss['is_pro'] == '0') {
                                        $count++;
                                    }
                                    $query_five = "SELECT * FROM " . T_USERS . " WHERE `referrer` = '{$fetched_datasss['user_id']}'";
                                    $sql_query_five = mysqli_query($sqlConnect, $query_five);

                                    if (mysqli_num_rows($sql_query_five)) {
                                        while ($fetched_datassss = mysqli_fetch_assoc($sql_query_five)) {
                                            if ($fetched_datassss['is_pro'] == '0') {
                                                $count++;
                                            }
                                        }
                                    }
                                }
                            }
                        }
                    }
                }
            }
        }
    }

    return $count;
}


function Wo_GetLevel1Referrers($user_id = 0)
{
    global $sqlConnect, $wo;

    if ($wo['loggedin'] == false) {
        return false;
    }

    if (empty($user_id)) {
        $user_id = Wo_Secure($wo['user']['user_id']);
    } else {
        $user_id = Wo_Secure($user_id);
    }

    $data = array();
    $count = 0;

    $query_one = "SELECT * FROM " . T_USERS . " WHERE `referrer` = '{$user_id}'";
    $sql_query_one = mysqli_query($sqlConnect, $query_one);

    if (mysqli_num_rows($sql_query_one)) {
        while ($fetched_data = mysqli_fetch_assoc($sql_query_one)) {
            if ($fetched_data['is_pro'] == '1') {
                $count++;
            }

            
        }
    }

    return $count;
}

function Wo_GetLevel2Referrers($user_id = 0)
{
    global $sqlConnect, $wo;

    if ($wo['loggedin'] == false) {
        return false;
    }

    if (empty($user_id)) {
        $user_id = Wo_Secure($wo['user']['user_id']);
    } else {
        $user_id = Wo_Secure($user_id);
    }

    $data = array();
    $count = 0;

    $query_one = "SELECT * FROM " . T_USERS . " WHERE `referrer` = '{$user_id}'";
    $sql_query_one = mysqli_query($sqlConnect, $query_one);

    if (mysqli_num_rows($sql_query_one)) {
        while ($fetched_data = mysqli_fetch_assoc($sql_query_one)) {
            
            $query_two = "SELECT * FROM " . T_USERS . " WHERE `referrer` = '{$fetched_data['user_id']}'";
            $sql_query_two = mysqli_query($sqlConnect, $query_two);

            if (mysqli_num_rows($sql_query_two)) {
                while ($fetched_datas = mysqli_fetch_assoc($sql_query_two)) {
                    if ($fetched_datas['is_pro'] == '1') {
                        $count++;
                    }

                   
                }
            }
        }
    }

    return $count;
}


function Wo_GetLevel3Referrers($user_id = 0)
{
    global $sqlConnect, $wo;

    if ($wo['loggedin'] == false) {
        return false;
    }

    if (empty($user_id)) {
        $user_id = Wo_Secure($wo['user']['user_id']);
    } else {
        $user_id = Wo_Secure($user_id);
    }

    $data = array();
    $count = 0;

    $query_one = "SELECT * FROM " . T_USERS . " WHERE `referrer` = '{$user_id}'";
    $sql_query_one = mysqli_query($sqlConnect, $query_one);

    if (mysqli_num_rows($sql_query_one)) {
        while ($fetched_data = mysqli_fetch_assoc($sql_query_one)) {
            

            $query_two = "SELECT * FROM " . T_USERS . " WHERE `referrer` = '{$fetched_data['user_id']}'";
            $sql_query_two = mysqli_query($sqlConnect, $query_two);

            if (mysqli_num_rows($sql_query_two)) {
                while ($fetched_datas = mysqli_fetch_assoc($sql_query_two)) {
                    

                    $query_three = "SELECT * FROM " . T_USERS . " WHERE `referrer` = '{$fetched_datas['user_id']}'";
                    $sql_query_three = mysqli_query($sqlConnect, $query_three);

                    if (mysqli_num_rows($sql_query_three)) {
                        while ($fetched_datass = mysqli_fetch_assoc($sql_query_three)) {
                            if ($fetched_datass['is_pro'] == '1') {
                                $count++;
                            }
                        }
                    }
                   
                }
            }
        }
    }

    return $count;
}

function Wo_GetLevel4Referrers($user_id = 0)
{
    global $sqlConnect, $wo;

    if ($wo['loggedin'] == false) {
        return false;
    }

    if (empty($user_id)) {
        $user_id = Wo_Secure($wo['user']['user_id']);
    } else {
        $user_id = Wo_Secure($user_id);
    }

    $data = array();
    $count = 0;

    $query_one = "SELECT * FROM " . T_USERS . " WHERE `referrer` = '{$user_id}'";
    $sql_query_one = mysqli_query($sqlConnect, $query_one);

    if (mysqli_num_rows($sql_query_one)) {
        while ($fetched_data = mysqli_fetch_assoc($sql_query_one)) {
            

            $query_two = "SELECT * FROM " . T_USERS . " WHERE `referrer` = '{$fetched_data['user_id']}'";
            $sql_query_two = mysqli_query($sqlConnect, $query_two);

            if (mysqli_num_rows($sql_query_two)) {
                while ($fetched_datas = mysqli_fetch_assoc($sql_query_two)) {
                    

                    $query_three = "SELECT * FROM " . T_USERS . " WHERE `referrer` = '{$fetched_datas['user_id']}'";
                    $sql_query_three = mysqli_query($sqlConnect, $query_three);

                    if (mysqli_num_rows($sql_query_three)) {
                        while ($fetched_datass = mysqli_fetch_assoc($sql_query_three)) {
                            // if ($fetched_datass['is_pro'] == '1') {
                            //     $count++;
                            // }
                            $query_four = "SELECT * FROM " . T_USERS . " WHERE `referrer` = '{$fetched_datass['user_id']}'";
                            $sql_query_four = mysqli_query($sqlConnect, $query_four);

                            if (mysqli_num_rows($sql_query_four)) {
                                while ($fetched_datasss = mysqli_fetch_assoc($sql_query_four)) {
                                    if ($fetched_datasss['is_pro'] == '1') {
                                        $count++;
                                    }
                                }
                            }
    
                        }

                   

                    }
                   
                }
            }
        }
    }

    return $count;
}

function Wo_GetLevel5Referrers($user_id = 0)
{
    global $sqlConnect, $wo;

    if ($wo['loggedin'] == false) {
        return false;
    }

    if (empty($user_id)) {
        $user_id = Wo_Secure($wo['user']['user_id']);
    } else {
        $user_id = Wo_Secure($user_id);
    }

    $data = array();
    $count = 0;

    $query_one = "SELECT * FROM " . T_USERS . " WHERE `referrer` = '{$user_id}'";
    $sql_query_one = mysqli_query($sqlConnect, $query_one);

    if (mysqli_num_rows($sql_query_one)) {
        while ($fetched_data = mysqli_fetch_assoc($sql_query_one)) {
            

            $query_two = "SELECT * FROM " . T_USERS . " WHERE `referrer` = '{$fetched_data['user_id']}'";
            $sql_query_two = mysqli_query($sqlConnect, $query_two);

            if (mysqli_num_rows($sql_query_two)) {
                while ($fetched_datas = mysqli_fetch_assoc($sql_query_two)) {
                    

                    $query_three = "SELECT * FROM " . T_USERS . " WHERE `referrer` = '{$fetched_datas['user_id']}'";
                    $sql_query_three = mysqli_query($sqlConnect, $query_three);

                    if (mysqli_num_rows($sql_query_three)) {
                        while ($fetched_datass = mysqli_fetch_assoc($sql_query_three)) {
                            // if ($fetched_datass['is_pro'] == '1') {
                            //     $count++;
                            // }
                            $query_four = "SELECT * FROM " . T_USERS . " WHERE `referrer` = '{$fetched_datass['user_id']}'";
                            $sql_query_four = mysqli_query($sqlConnect, $query_four);

                            if (mysqli_num_rows($sql_query_four)) {
                                while ($fetched_datasss = mysqli_fetch_assoc($sql_query_four)) {


                                    $query_five = "SELECT * FROM " . T_USERS . " WHERE `referrer` = '{$fetched_datasss['user_id']}'";
                                    $sql_query_five = mysqli_query($sqlConnect, $query_five);

                                    if (mysqli_num_rows($sql_query_five)) {
                                        while ($fetched_datassss = mysqli_fetch_assoc($sql_query_five)) {
        
                                    if ($fetched_datassss['is_pro'] == '1') {
                                        $count++;
                                    }
                                }
                            }
                                }
                            }
    
                        }

                   

                    }
                   
                }
            }
        }
    }

    return $count;
}
```
