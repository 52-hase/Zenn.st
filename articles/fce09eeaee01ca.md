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

# クラスとは？

・クラスとは「レシピブック」や「設計図」のようなものです。下記のように`MyClass`は特定のタイプのオブジェクトの設計図であり、その中に`class_method`という手順が定義されています。

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
⇩ 記載

```
class Cookbook（レシピ本）
  def hamburger_recipe（ハンバーガーのレシピ）
    puts "class method: Hamburger Recipe"（ハンバーガーの作り方）
  end
end

Cookbook.hamburger_recipe  # => "class method: Hamburger Recipe"（ハンバーガーの作り方）
```

::::
