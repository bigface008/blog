---
title: 体系结构笔记
date: 2019-04-19 13:48:34
toc: true
tags:
- learn
- architecture
categories:
- architecture
---
本文用于记录体系结构课程的笔记。
>我也知道这很尴尬，但是我也没别的办法不是么！
<!--more-->

# 2019/4/19

## Evaluation Metrics

### Typical metrics
- Events frequency
- Interval durations
- Parameter sizes

### Characteristics of good metrics
- Allows unambiguous comparison
- Allows one to develop models
- Meaningful and easy to estimate

### A general classification
- Nominal(标定的，额定的) is better metrics. e.g., utilization

## Amdahl's Law
...

## Calculating CPI
请看PPT。

## Memory Performance Analysis
请看PPT。(重要)

## Little's Law

## Another Example: BW(Bandwidth) Estimation
请看PPT。(重要)

### Factors that affect BW
- Cache miss
- Data prefetch

BW = outstanding requests / average latency of a single request
= (LLC misses + prefetches) * #threads * cache line size access latency + contention latency

## Usefulness of Little's Law in Practice
请看PPT。(重要)

## On The Evaluation of Energy and Power

### Dynamic Power

### Frequency typically scales linerarly with voltage

## Server Speed vs. Server Power
- Experimental results show that power-to-speed relationship **is almost linear**
