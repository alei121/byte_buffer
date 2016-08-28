# byte_buffer
... still in progress ...

C implementation of Java ByteBuffer

Aligns to most methods in Java ByteBuffer

|ByteBuffer's methods  |byte_buffer functions   |
|---|---|
|static ByteBuffer allocate(int capacity)| |
|static ByteBuffer allocateDirect(int capacity)| |
|byte[] array()| |
|int arrayOffset()| |
|abstract CharBuffer asCharBuffer()| |
|abstract DoubleBuffer asDoubleBuffer()| |
|abstract FloatBuffer asFloatBuffer()| |
|abstract IntBuffer asIntBuffer()| |
|abstract LongBuffer asLongBuffer()| |
|abstract ByteBuffer asReadOnlyBuffer()| |
|abstract ShortBuffer asShortBuffer()| |
|abstract ByteBuffer compact()| |
|int compareTo(ByteBuffer that)| |
|abstract ByteBuffer duplicate()| |
|boolean equals(Object ob)| |
|abstract byte get()| |
|ByteBuffer get(byte[] dst)| |
|ByteBuffer get(byte[] dst, int offset, int length)| |
|abstract byte get(int index)| |
|abstract char getChar()| |
|abstract char getChar(int index)| |
|abstract double getDouble()| |
|abstract double getDouble(int index)| |
|abstract float getFloat()| |
|abstract float getFloat(int index)| |
|abstract int getInt()| |
|abstract int getInt(int index)| |
|abstract long getLong()| |
|abstract long getLong(int index)| |
|abstract short getShort()| |
|abstract short getShort(int index)| |
|boolean hasArray()| |
|int hashCode()| |
|abstract boolean isDirect()| |
|ByteOrder order()| |
|ByteBuffer order(ByteOrder bo)| |
|abstract ByteBuffer put(byte b)| |
|ByteBuffer put(byte[] src)| |
|ByteBuffer put(byte[] src, int offset, int length)| |
|ByteBuffer put(ByteBuffer src)| |
|abstract ByteBuffer put(int index, byte b)| |
|abstract ByteBuffer putChar(char value)| |
|abstract ByteBuffer putChar(int index, char value)| |
|abstract ByteBuffer putDouble(double value)| |
|abstract ByteBuffer putDouble(int index, double value)| |
|abstract ByteBuffer putFloat(float value)| |
|abstract ByteBuffer putFloat(int index, float value)| |
|abstract ByteBuffer putInt(int value)| |
|abstract ByteBuffer putInt(int index, int value)| |
|abstract ByteBuffer putLong(int index, long value)| |
|abstract ByteBuffer putLong(long value)| |
|abstract ByteBuffer putShort(int index, short value)| |
|abstract ByteBuffer putShort(short value)| |
|abstract ByteBuffer slice()| |
|String toString()| |
|static ByteBuffer wrap(byte[] array)| |
|static ByteBuffer wrap(byte[] array, int offset, int length)| |
|abstract Object array()| |
|abstract int arrayOffset()| |
|int capacity()| |
|Buffer clear()| |
|Buffer flip()| |
|abstract boolean hasArray()| |
|boolean hasRemaining()| |
|abstract boolean isDirect()| |
|abstract boolean isReadOnly()| |
|int limit()| |
|Buffer limit(int newLimit)| |
|Buffer mark()| |
|int position()| |
|Buffer position(int newPosition)| |
|int remaining()| |
|Buffer reset()| |
|Buffer rewind()| |

