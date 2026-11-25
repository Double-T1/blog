+++
date = '2026-11-26T12:47:31+08:00'
title = 'Memory usage of go struct based on the sequnce of fields'
tags = ['go','performance']
+++

# Overview
This is a PR review i got during work, where the sequnce of field placement affects the totla memory usage

'''
type ex1 struct {
    a int
    b string
    c int64
    d bool
    e *int
}
'''

'''
type ex1 struct {
    a int
    d bool
    b string
    c int64
    e *int
}
'''
