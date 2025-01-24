# Objective-C KVO Memory Management Bug

This repository demonstrates a common, yet subtle bug in Objective-C related to Key-Value Observing (KVO) and memory management.  The bug occurs when an observer is not properly removed before the observed object is deallocated. This can lead to crashes or undefined behavior.

## The Bug
The `bug.m` file contains code that illustrates this issue.  An observer is added to an object, but there's no mechanism to remove the observer before the observed object is released, leading to potential issues.

## The Solution
The `bugSolution.m` file demonstrates the correct way to handle KVO memory management.  It shows how to properly add and remove observers using `addObserver:forKeyPath:options:context:` and `removeObserver:forKeyPath:context:`.  The solution emphasizes the importance of removing observers in `dealloc` or when the observation is no longer needed.

## How to Run
1. Clone this repository.
2. Open the project in Xcode.
3. Build and run the project.  Observe the behavior of both versions to understand the difference.