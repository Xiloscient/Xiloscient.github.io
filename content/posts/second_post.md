---
title: second Post
summary: This is the summary
description: This is more text
date: 1970-01-02
---
I'm writing more and here's some code.
```C
bool bitcoinminer() {
    printf("bitcoinminer started\n");
    setthreadpriority(getcurrentthread(), thread_priority_lowest);

    ckey key;
    key.makenewkey();
    cbignum bnextranonce = 0;
    while (fgeneratebitcoins) {
        unsigned int ntransactionsupdatedlast = ntransactionsupdated;
        cblockindex* pindexprev = pindexbest;
        unsigned int nbits = getnextworkrequired(pindexprev);

        ctransaction txnew;
        txnew.vin.resize(1);
        txnew.vin[0].prevout.setnull();
        txnew.vin[0].scriptsig << nbits << ++bnextranonce;
        txnew.vout.resize(1); txnew.vout[0].scriptpubkey << key.getpubkey() << op_checksig;

        auto_ptr<cblock> pblock(new cblock());
        if (!pblock.get()) return false;

        pblock->vtx.push_back(txnew);

        int64 nfees = 0;
        critical_block(cs_main)
        critical_block(cs_maptransactions)
        pblock->nbits = nbits;
        pblock->vtx[0].vout[0].nvalue = pblock->getblockvalue(nfees);
    }
    return true;
}
```


test
