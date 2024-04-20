---
title: "クラスメソッド と インスタンスメソッド の違いについて"
emoji: "⚖️"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: [クラスメソッド, インスタンスメソッド]
published: false
---

# 目的

クラスメソッド と インスタンスメソッド の違いについて学習した内容を記載します。

# 内容

# クラスメソッド とは？
クラスメソッドは、あるクラスに属するメソッドのうち、そのクラス自体に関連する操作や振る舞いを定義するためのメソッドです。クラスメソッドは、インスタンスを生成せずに直接クラスに対して呼び出すことができます。

# クラスとは？ メソッドとは？

・```クラス```とは「設計図」のようなものです。下記のように`MyClass`は特定のタイプのオブジェクトの設計図です。
・```メソッド```とは処理や振る舞いを定義する役割があります。例では`class_method`で記載されています。

[例]
```
class MyClass
  def class_method
    puts "class method"
  end
end

MyClass.class_method  # => "class method"
```

::::details MyClass を レシピ本 に例えた場合
```
class MyClass（レシピ本）
  def self.class_method（ハンバーガーのレシピ）
    puts "This is a class method"（ハンバーガーの作り方）
  end
end

MyClass.class_method  # => "This is a class method"（ハンバーガーの作り方）
```
　⇩ コードの記載

```
class Cookbook（レシピ本）
  def hamburger_recipe（ハンバーガーのレシピ）
    puts "class method: Hamburger Recipe"（ハンバーガーの作り方）
  end
end

Cookbook.hamburger_recipe  # => "class method: Hamburger Recipe"（ハンバーガーの作り方）
```
::::

# クラスメソッド と インスタンスメソッドの違い
一般的なインスタンスメソッドは、クラスから生成されたインスタンスに対して呼び出され、そのインスタンスの特定の状態や振る舞いに対する操作を行います。一方、クラスメソッドはクラス自体に関連し、そのクラス全体に影響を与える操作を提供します。

クラスメソッドの例
```
class MyClass
  def self.class_method
    puts "This is a class method"
  end
end

# クラスメソッドを呼び出す方法
MyClass.class_method
```

インスタンスメソッドの例
```
class MyClass
  def instance_method
    puts "This is an instance method"
  end
end

# インスタンスを作成
my_object = MyClass.new

# インスタンスメソッドを呼び出す方法
my_object.instance_method
```
クラスメソッドはクラスに関連付けられており、クラス名を使って直接呼び出されます。
インスタンスメソッドはオブジェクトに関連付けられており、そのオブジェクトを介して呼び出されます。