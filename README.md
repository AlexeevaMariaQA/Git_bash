<h1 tabindex="-1" class="heading-element" dir="auto">📌 Работа с bash</h1>

Если на проекте есть доступ к серверу, то тестировщик может просматривать логи или другие артефакты на нем. Для этого может пригодиться знание команд bash.

<h2 tabindex="-1" class="heading-element" dir="auto">Задание 1</h2>

<pre><span class="pl-k">~</span>                                     <span class="pl-c"><span class="pl-c">#</span> Home directory </span>
<span class="pl-c1">pwd</span>                                   <span class="pl-c"><span class="pl-c">#</span> Show current directory path</span>
mkdir test1                           <span class="pl-c"><span class="pl-c">#</span> Create a directory named test1</span>
<span class="pl-c1">cd</span> test1                              <span class="pl-c"><span class="pl-c">#</span> Go to directory test1 (also possible to write the path to needed directory)</span>
touch file{1,2,3}.txt.                <span class="pl-c"><span class="pl-c">#</span> Create file 1,2 and 3 inside directory test1</span>
ls                                    <span class="pl-c"><span class="pl-c">#</span> Check directory test1 content (ls -la if there are any hidden files) </span>
<span class="pl-c1">cd</span>                                    <span class="pl-c"><span class="pl-c">#</span> Go home directory </span>
mkdir test2                           <span class="pl-c"><span class="pl-c">#</span> Create directory test2 inside home directory</span>
rmdir test2                           <span class="pl-c"><span class="pl-c">#</span> Delete directory test2 </span>
<span class="pl-c1">cd</span> mv <span class="pl-k">~</span>/test1                         <span class="pl-c"><span class="pl-c">#</span> Go back to directory test1</span>
rm file2.txt                          <span class="pl-c"><span class="pl-c">#</span> Delete file 2 </span>
mkdir test3                           <span class="pl-c"><span class="pl-c">#</span> Create directory test3</span>
touch file{4,5}.txt                   <span class="pl-c"><span class="pl-c">#</span> Add two files to directory test3</span>
<span class="pl-c1">cd</span> ..                                 <span class="pl-c"><span class="pl-c">#</span> Go back to parent directory</span>
rmdir -rf test3                       <span class="pl-c"><span class="pl-c">#</span> Delete directory test3  </span>
ls                                    <span class="pl-c"><span class="pl-c">#</span> Make sure directory test3 was deleted</span>
mkdir test4                           <span class="pl-c"><span class="pl-c">#</span> Create directory test4</span>
mv <span class="pl-k">~</span>/test1/file{1,3}.txt <span class="pl-k">~</span>/test4      <span class="pl-c"><span class="pl-c">#</span> Move file1.txt and file3.txt from directory test1 to directory test4</span>
<span class="pl-c1">echo</span> line11 <span class="pl-k">&gt;&gt;</span> file1.txt              <span class="pl-c"><span class="pl-c">#</span> Add 3 lines to file1.txt</span>
<span class="pl-c1">echo</span> line12 <span class="pl-k">&gt;&gt;</span> file1.txt            
<span class="pl-c1">echo</span> line13 <span class="pl-k">&gt;&gt;</span> file1.txt
cat file1.txt                         <span class="pl-c"><span class="pl-c">#</span> Check content of file1.txt</span>
<span class="pl-c1">echo</span> line31 <span class="pl-k">&gt;&gt;</span> file3.txt              <span class="pl-c"><span class="pl-c">#</span> Add 3 lines to file3.txt</span>
<span class="pl-c1">echo</span> line32 <span class="pl-k">&gt;&gt;</span> file3.txt
<span class="pl-c1">echo</span> line33 <span class="pl-k">&gt;&gt;</span> file3.txt
cat file1.txt file3.txt               <span class="pl-c"><span class="pl-c">#</span> Check contents of file1.txt and file3.txt at once</span>
nano file1.txt + manual replacement   <span class="pl-c"><span class="pl-c">#</span> Using one of the editors, replace all lines in file1.txt and file3.txt</span>
nano file3.txt + manual replacement </pre>

<h2 tabindex="-1" class="heading-element" dir="auto">Задание 2</h2>

<pre>mkdir test3                                   <span class="pl-c"><span class="pl-c">#</span> Create directory test3 </span>
<span class="pl-c1">cd</span> test3                                      <span class="pl-c"><span class="pl-c">#</span> Open directory test3 </span>
<span class="pl-c1">echo</span> -e <span class="pl-s"><span class="pl-pds">"</span>row1\nrow2\nrow3\nrow4<span class="pl-pds">"</span></span> <span class="pl-k">&gt;</span> file4.txt  <span class="pl-c"><span class="pl-c">#</span> Add 3 files to test3, each of which should contain 4 lines</span>
<span class="pl-c1">echo</span> -e <span class="pl-s"><span class="pl-pds">"</span>row1\nrow2\nrow3\nrow4<span class="pl-pds">"</span></span> <span class="pl-k">&gt;</span> file5.txt  
<span class="pl-c1">echo</span> -e <span class="pl-s"><span class="pl-pds">"</span>row1\nrow2\nrow3\nrow4<span class="pl-pds">"</span></span> <span class="pl-k">&gt;</span> file6.txt 
grep <span class="pl-s"><span class="pl-pds">"</span>row2<span class="pl-pds">"</span></span> file5.txt                         <span class="pl-c"><span class="pl-c">#</span> Find the line "row2" in file5.txt </span>
grep -R <span class="pl-s"><span class="pl-pds">"</span>row<span class="pl-pds">"</span></span> <span class="pl-c1">.</span>                               <span class="pl-c"><span class="pl-c">#</span> Find the line "row" in the test3 directory</span>
grep -c <span class="pl-s"><span class="pl-pds">"</span>row<span class="pl-pds">"</span></span> file6.txt                       <span class="pl-c"><span class="pl-c">#</span> Count number of lines containing word "row" in file6.txt</span>
find <span class="pl-c1">.</span> -name <span class="pl-s"><span class="pl-pds">"</span>file5.txt<span class="pl-pds">"</span></span>                      <span class="pl-c"><span class="pl-c">#</span> Find file5.txt in test3 directory</span>
find <span class="pl-c1">.</span> -name <span class="pl-s"><span class="pl-pds">"</span>file5.txt<span class="pl-pds">"</span></span> -delete              <span class="pl-c"><span class="pl-c">#</span> Using find command delete file5.txt</span>
<span class="pl-c1">echo</span> <span class="pl-c1">test</span> <span class="pl-k">&gt;</span> file4.txt                         <span class="pl-c"><span class="pl-c">#</span> Using the echo command, add the word "test" to file4.txt</span>
sed <span class="pl-s"><span class="pl-pds">'</span>s/test/fail/g<span class="pl-pds">'</span></span> file4.txt                 <span class="pl-c"><span class="pl-c">#</span> Change the word "test" in file4.txt to "fail"</span>
<span class="pl-c1">echo</span> <span class="pl-c1">test</span> <span class="pl-k">&gt;&gt;</span> file4.txt                        <span class="pl-c"><span class="pl-c">#</span> Add the word "test" to file4.txt so that the content is preserved</span>
ps aux                                        <span class="pl-c"><span class="pl-c">#</span> View all processes in the system</span>
<span class="pl-c1">kill</span> 666                                      <span class="pl-c"><span class="pl-c">#</span> Kill process 666 in console</span>
ping artsiomrusau.com                         <span class="pl-c"><span class="pl-c">#</span> Check the availability of the website artsiomrusau.com using ping</span>
ping -c 5 artsiomrusau.com                    <span class="pl-c"><span class="pl-c">#</span> Send 5 packages to artsiomrusau.com  </span>
curl https://petstore.swagger.io/v2/pet/      <span class="pl-c"><span class="pl-c">#</span> Using GET and cURL command, get info about registered pets at petstore.swagger.io</span>
findByStatus<span class="pl-k">?</span>status=registered                
curl -X POST https://petstore.swagger.io/     <span class="pl-c"><span class="pl-c">#</span> Using POST and cURL command, create a new user at petstore.swagger.io</span>
v2/user --data <span class="pl-s"><span class="pl-pds">"</span>id=1<span class="pl-pds">"</span></span> 
--data <span class="pl-s"><span class="pl-pds">"</span>username=Darrel_Volkman80<span class="pl-pds">"</span></span> 
--data <span class="pl-s"><span class="pl-pds">"</span>firstName=Darrel<span class="pl-pds">"</span></span> 
--data <span class="pl-s"><span class="pl-pds">"</span>lastName=Volkman<span class="pl-pds">"</span></span> 
--data <span class="pl-s"><span class="pl-pds">"</span>email=Darrel_Volkman80@gmail.com<span class="pl-pds">"</span></span> 
--data <span class="pl-s"><span class="pl-pds">"</span>password=g8kq2W1z_utLEBs<span class="pl-pds">"</span></span> 
--data <span class="pl-s"><span class="pl-pds">"</span>phone=7442783865<span class="pl-pds">"</span></span> 
--data <span class="pl-s"><span class="pl-pds">"</span>userStatus=0<span class="pl-pds">"</span></span></pre>
