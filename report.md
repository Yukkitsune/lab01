## Tasks
1. Скачайте библиотеку boost с помощью утилиты wget. Адрес для скачивания https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz.
2. Разархивируйте скаченный файл в директорию ~/boost_1_69_0
3. Подсчитайте количество файлов в директории ~/boost_1_69_0 не включая вложенные директории.
4. Подсчитайте количество файлов в директории ~/boost_1_69_0 включая вложенные директории.
5. Подсчитайте количество заголовочных файлов, файлов с расширением .cpp, сколько остальных файлов (не заголовочных и не .cpp).
6. Найдите полный пусть до файла any.hpp внутри библиотеки boost.
7. Выведите в консоль все файлы, где упоминается последовательность boost::asio.
8. Скомпилирутйе boost. Можно воспользоваться инструкцией или ссылкой.
9. Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию ~/boost-libs.
10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.
11. Найдите топ10 самых "тяжёлых".
## Work
1. $ wget https://sourceforge.net/projects/boost/files/boost/1.84.0/boost_1_84_0.tar.gz
2. $ tar -xvf boost_1_84_0.tar.gz  
3. $ find . -maxdepth 1 -type f | wc -l  13  ![image](https://github.com/Yukkitsune/lab01/assets/29312710/1ba1071e-ae05-49d9-9bd3-b3ee9c3289e4)
4. $ find . -type f | wc - l  76801  ![image](https://github.com/Yukkitsune/lab01/assets/29312710/eff0c687-8369-4de5-ac56-64d3468ccdc7)
5. 
   - Заголовочные файлы $ find . -type f -name "*.hpp" -o -name "*.h" | wc -l  17487  ![image](https://github.com/Yukkitsune/lab01/assets/29312710/0d715f7d-c288-4813-99bc-9a7e48ecfda0)
   - Файлы .cpp $ find . -type f -name "*.cpp" | wc -l  17337  ![image](https://github.com/Yukkitsune/lab01/assets/29312710/40f8b79e-19c4-4fb5-863c-9b3a0f9c09c4)
   - Остальные файлы $ find . -type f -not -name "*.hpp" -not -name "*.h" -not -name "*.cpp"  | wc -l  41977  ![image](https://github.com/Yukkitsune/lab01/assets/29312710/e1c8f036-6330-48cf-b614-5ebb1c3b68d0)
6. $ export PATH=${PATH}:`pwd`/boost/any.hpp  
   $ echo ${PATH}
   /home/kitsune/.local/bin:/home/kitsune/bin:/usr/local/bin:/usr/local/sbin:/usr/bin:/usr/sbin:/home/kitsune/Yukkitsune/workspace/boost_1_84_0/boost/any.hpp
   ![image](https://github.com/Yukkitsune/lab01/assets/29312710/4d44ea52-dd9c-49d9-97e6-8b812b3affc3)
7. $ grep -ril "boost::asio"
   ![image](https://github.com/Yukkitsune/lab01/assets/29312710/88840e7b-0dd4-4be2-b11e-318a4907dd2f)
8. $ ./bootstrap.sh --prefix=boost_output --with-python=python3
   $ ./b2 install -j 12
   ![image](https://github.com/Yukkitsune/lab01/assets/29312710/9ccc108a-65d7-46ca-946f-66af22c8dd5e)
9. $ cd boost_output &&  mv ./lib ~/boost-libs && cd ~/boost-libs
   ![image](https://github.com/Yukkitsune/lab01/assets/29312710/46aaa008-0980-4d7c-9c94-7e23bab8d8f8)
10. $ ls -lh  41Mb
    ![image](https://github.com/Yukkitsune/lab01/assets/29312710/17103682-32fc-4f4e-9af6-636aed1e4804)
11. $ ls -lS | head -n 11
    ![image](https://github.com/Yukkitsune/lab01/assets/29312710/d4aa4d7a-6a5c-4edc-9f76-d66870cabed1)

    
     

   

   

