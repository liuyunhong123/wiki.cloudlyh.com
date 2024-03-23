---
title: 2.anaconda基础操作
description: anaconda基础操作
published: true
date: 2024-03-23T05:23:33.796Z
tags: anaconda
editor: markdown
dateCreated: 2024-03-23T03:31:07.742Z
---

## 1. 打开打开Anaconda Powershell Prompt
![打开anacondapowershellprompt.png](/wiki/python/anaconda/conda基础操作/打开anacondapowershellprompt.png)

## 2. 查看当前环境列表
```
conda env list
```
![查看当前环境列表.png](/wiki/python/anaconda/conda基础操作/查看当前环境列表.png)

## 3. conda创建环境
```
conda create -n mydjango python
```
输入y确定创建环境
![conda创建环境.png](/wiki/python/anaconda/conda基础操作/conda创建环境.png)

## 4. conda激活环境
```
conda activate myjango
```
![conda激活环境.png](/wiki/python/anaconda/conda基础操作/conda激活环境.png)

## 5. conda删除环境
### 1. 退出当前环境
```
conda deactivate
```
### 2. 删除mydjango环境
```
conda remove -n mydjango --all
```
### 3. 查看当前环境
```
conda env list
```
![conda删除环境.png](/wiki/python/anaconda/conda基础操作/conda删除环境.png)




