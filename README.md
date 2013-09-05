CryptImpHook
============

Status: [![Build Status](https://travis-ci.org/neurogeek/python-crypt-import-hooks.png?branch=master)](https://travis-ci.org/neurogeek/python-crypt-import-hooks)

    /*!
     * \mainpage CryptImpHook.c
     *
     * \version 1.0
     * \date 2011
     * \author Jesus Rivero (Neurogeek) <neurogeekster@gmail.com>, <neurogeek@gentoo.org>
     *
     * \section Main
     *  CryptImpHook is a CPython Import Hook (see PEP-302) that allows encrypted Python modules
     *  to be used in a transparent manner in any Python application. The encrypted
     *  modules have a .pye extension.
     *
     *  This code is just a proof-of-concept and implements the XOR encryption
     *  with a given key. If you would like to change the encryption cipher or mechanism, you could
     *  implement yours by re_writing the cih_read_module_code function.
     *
     *  This is public domain code.
     */

To build & test, just run: make && make test
For docs, run: make docs

This requires Python =< 2.7 to run.

You will find the key in src/CryptImpHook.h.
To encrypt your Python modules, use dist/CryptConv <source_file> <dest_file>
Encrypted Python modules will have a .pye extension.


Disclaimer:

XOR cipher is not a strong encryption algorithm. You should not use this code in Production systems. 
This is just a proof-of-concept, to be completely useful, you should implement the encryption/decryption with some
proven algorithm or cipher, like AES or 3DES, use a large char[] for your key, and add -O2 to the code so it gets harder
for anybody to dissect the key.
