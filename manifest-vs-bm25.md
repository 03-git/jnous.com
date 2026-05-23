title: Manifest vs BM25
summary: Manifest-routed retrieval beats BM25 for small-corpus QA. The routing table knows which document answers the question. BM25 guesses.
date: 2026-05-10
url: https://jnous.com/manifest-vs-bm25.md
source: controlled experiment (subtract.ing + Lua 5.4 corpora, qwen2.5-7b + sonnet-4-6, four-scorer blind evaluation)
license: GPLv2


MANIFEST VS BM25

RESULT

       Two retrieval methods. Same corpus. Same questions. Same models
       scoring the answers.

       Manifest routing: a human-curated table maps question categories
       to documents. The system looks up which document to read before
       reading it.

       BM25: term-frequency ranking across the corpus. The system
       searches all documents and picks the best-matching passages.

       Manifest wins. It retrieves the right document because a human
       already decided which document answers which kind of question.
       BM25 retrieves the most lexically similar passage, which is
       not always the right one.

WHY

       Small corpora don't have enough documents for statistical
       retrieval to distinguish signal from noise. BM25 works when
       thousands of documents compete and term frequency is meaningful.
       With dozens of documents, a routing table that says "questions
       about X go to document Y" is more reliable than term counting.

       The manifest is cheaper to build than it looks. The human
       already knows which documents answer which questions — that's
       why they wrote them.

DATA
       raw.githubusercontent.com/03-git/variance-lab/main/findings/13-manifest-vs-bm25.txt
