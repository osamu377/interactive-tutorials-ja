Tutorial
--------

### Introduction

The C programming language is a general purpose programming language, which relates closely to the way machines work. 
Understanding how computer memory works is an important aspect of the C programming language. Although C can be considered
as "hard to learn", C is in fact a very simple language, with very powerful capabilities.

C is a very common language, and it is the language of many applications such as Windows, the Python interpreter, Git, and
many many more. 

C is a compiled language - which means that in order to run it, the compiler (for example, GCC or Visual Studio) must take the code that 
we wrote, process it, and then create an executable file. This file can then be executed, and will do what we intended for the program
to do.

C言語は汎用プログラミング言語であり、機械の動作と密接に関連しています。
コンピュータメモリの仕組みを理解することは、C言語の重要な側面です。C言語は「習得が難しい」と考えられがちですが、実際には非常にシンプルな言語であり、非常に強力な機能を備えています。

C言語は非常に一般的な言語であり、Windows、Pythonインタープリター、Gitなど、多くのアプリケーションの言語となっています。

C言語はコンパイル言語です。つまり、C言語を実行するには、コンパイラ（GCCやVisual Studioなど）が記述したコードを受け取り、処理して、実行ファイルを作成する必要があります。
このファイルは実行可能であり、プログラムに期待した動作を実行します。

### Our first program

Every C program uses libraries, which give the ability to execute necessary functions. For example, the most basic function
called `printf`, which prints to the screen, is defined in the `stdio.h` header file. 

To add the ability to run the `printf` command to our program, we must add the following include directive to our first line of the code:

すべてのCプログラムは、必要な関数を実行するためのライブラリを使用します。例えば、画面に出力する最も基本的な関数である「printf」は、「stdio.h」ヘッダーファイルで定義されています。

プログラムに「printf」コマンドを実行する機能を追加するには、コードの1行目に次のincludeディレクティブを追加する必要があります。

    #include <stdio.h>

The second part of the code is the actual code which we are going to write. The first code which will run will always reside 
in the `main` function. 

コードの2番目の部分は、実際に記述するコードです。最初に実行されるコードは、常に
`main` 関数内にあります。

    int main() {
      ... our code goes here
    }

The `int` keyword indicates that the function `main` will return an integer - a simple number. The number which will be returned
by the function indicates whether the program that we wrote worked correctly. If we want to say that our code
was run successfully, we will return the number 0. A number greater than 0 will mean that the program that we wrote failed.

`int` キーワードは、関数 `main` が整数、つまり単純な数値を返すことを示します。関数によって返される数値は、記述したプログラムが正しく動作したかどうかを示します。コードが正常に実行されたことを示す場合は、数値 0 を返します。0 より大きい数値は、記述したプログラムが失敗したことを意味します。

For this tutorial, we will return 0 to indicate that our program was successful:

このチュートリアルでは、プログラムが成功したことを示すために 0 を返します。

    return 0;

Notice that every statement in C must end with a semicolon, so that the compiler knows that a new statement has started.

Last but not least, we will need to call the function `printf` to print our sentence.

C言語のすべての文はセミコロンで終わる必要があることに注意してください。これにより、コンパイラは新しい文が始まったことを認識します。

最後に、文を出力するために関数「printf」を呼び出す必要があります。

Exercise
--------

Change the program at the bottom so that it prints to the output "Hello, World!". 

下部のプログラムを変更して、出力に「Hello, World!」と表示されるようにします。

Tutorial Code
-------------

    #include <stdio.h>

    int main() {
      printf("Goodbye, World!");
      return 0;
    }

Expected Output
---------------

    Hello, World!

Solution
--------

    #include <stdio.h>

    int main() {
      printf("Hello, World!");
      return 0;
    }
