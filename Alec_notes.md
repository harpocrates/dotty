Need a subclass of `MethodVisitor` that:

  - includes more methods (eg. for more aware bytecode gen)
     * `iload`, `iconst`, etc.

  - tracks reachability (so we don't constantly generate dead code)
    * `from.isNothingType` in `adapt` checks for reachability before `athrow`

  - override return instructions if needed (see `appendToStaticCtor` and `foreachInsn`)

  - track flags associated with labels (see `LabelNode1`)

Android stuff:

 * If class extends `android.os.Parcelable`, then it must:

     - have a static `CREATOR` field of type `android.os.Parcelable$Creator`
