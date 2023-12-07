# README

Version of the `lh-workshop` materials, but designed to work locally and with the GHC plugin.

### Doing the workshop

**Step 1**

Install prerequisites

- [`z3`](https://github.com/exercism/z3/blob/main/docs/INSTALLATION.md)
- [Haskell](https://www.haskell.org/ghcup/)

**Step 2**

clone this repository

**Step 3**

Fire up the LH by running

```bash
$ stack build --fast --file-watch
```

**Step 4**

Then edit the files in `src` in the order

1. `src/M02Refinements.lhs`
2. `src/M03DataTypes.lhs`
3. `src/M04InsertSort.lhs`
4. `src/M05Eval.lhs`
5. `src/M06ByteString.lhs`

to first  **delete** the line

```haskell
{-@ LIQUID "--compile-spec" @-}
```

which will induce LH to report a bunch of type errors for that module,
and then iteratively fix the refinement type errors, before moving to the
next file.

Enjoy!

### Troubleshooting

If you use vscode or other HLS compatible editors, stuff _usually_ just works
BUT sometimes the LH plugin gets fed code that *GHC* doesn't like (e.g. duplicate
or missing definitions, or odd type errors, and in that case you get a wierd `"Uh Oh."`
panic in the editor. We recommend using `stack build --fast --file-watch` in a terminal
to get the GHC errors there too, as somehow that is more robust than the HLS integration...