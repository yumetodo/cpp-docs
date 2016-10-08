---
title: "concurrent_unordered_map Class"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: b2d879dd-87ef-4af9-a266-a5443fd538b8
caps.latest.revision: 11
manager: ghogen
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pl-pl
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
---
# concurrent_unordered_map Class
The `concurrent_unordered_map` class is a concurrency-safe container that controls a varying-length sequence of elements of type `std::pair<const _Key_type, _Element_type>`. The sequence is represented in a way that enables concurrency-safe append, element access, iterator access, and iterator traversal operations.  
  
## Syntax  
  
```  
template <  
    typename _Key_type,  
    typename _Element_type,  
    typename _Hasher = std::tr1::hash< _Key_type>,  
    typename _Key_equality = std::equal_to< _Key_type>,  
    typename _Allocator_type = std::allocator<std::pair<const _Key_type, _Element_type> >  
>,typename _Key_equality = std::equal_to< _Key_type>, typename _Allocator_type = std::allocator<std::pair<const _Key_type, _Element_type> > > class concurrent_unordered_map : public details::_Concurrent_hash< details::_Concurrent_unordered_map_traits< _Key_type, _Element_type, details::_Hash_compare< _Key_type, _Hasher, _Key_equality>, _Allocator_type, false> >;  
```  
  
#### Parameters  
 `_Key_type`  
 The key type.  
  
 `_Element_type`  
 The mapped type.  
  
 `_Hasher`  
 The hash function object type. This argument is optional and the default value is `std::tr1::hash<``_Key_type``>`.  
  
 `_Key_equality`  
 The equality comparison function object type. This argument is optional and the default value is `std::equal_to<``_Key_type``>`.  
  
 `_Allocator_type`  
 The type that represents the stored allocator object that encapsulates details about the allocation and deallocation of memory for the concurrent unordered map. This argument is optional and the default value is `std::allocator<std::pair<``_Key_type`, `_Element_type``>>`.  
  
## Members  
  
### Public Typedefs  
  
|Name|Description|  
|----------|-----------------|  
|`allocator_type`|The type of an allocator for managing storage.|  
|`const_iterator`|The type of a constant iterator for the controlled sequence.|  
|`const_local_iterator`|The type of a constant bucket iterator for the controlled sequence.|  
|`const_pointer`|The type of a constant pointer to an element.|  
|`const_reference`|The type of a constant reference to an element.|  
|`difference_type`|The type of a signed distance between two elements.|  
|`hasher`|The type of the hash function.|  
|`iterator`|The type of an iterator for the controlled sequence.|  
|`key_equal`|The type of the comparison function.|  
|`key_type`|The type of an ordering key.|  
|`local_iterator`|The type of a bucket iterator for the controlled sequence.|  
|`mapped_type`|The type of a mapped value associated with each key.|  
|`pointer`|The type of a pointer to an element.|  
|`reference`|The type of a reference to an element.|  
|`size_type`|The type of an unsigned distance between two elements.|  
|`value_type`|The type of an element.|  
  
### Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[concurrent_unordered_map::concurrent_unordered_map Constructor](#concurrent_unordered_map__concurrent_unordered_map_constructor)|Overloaded. Constructs a concurrent unordered map.|  
  
### Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[concurrent_unordered_map::at Method](#concurrent_unordered_map__at_method)|Overloaded. Finds an element in a `concurrent_unordered_map` with a specified key value.. This method is concurrency-safe.|  
|[concurrent_unordered_map::hash_function Method](#concurrent_unordered_map__hash_function_method)|Gets the stored hash function object.|  
|[concurrent_unordered_map::insert Method](#concurrent_unordered_map__insert_method)|Overloaded. Adds elements to the `concurrent_unordered_map` object.|  
|[concurrent_unordered_map::key_eq Method](#concurrent_unordered_map__key_eq_method)|Gets the stored equality comparison function object.|  
|[concurrent_unordered_map::swap Method](#concurrent_unordered_map__swap_method)|Swaps the contents of two `concurrent_unordered_map` objects. This method is not concurrency-safe.|  
|[concurrent_unordered_map::unsafe_erase Method](#concurrent_unordered_map__unsafe_erase_method)|Overloaded. Removes elements from the `concurrent_unordered_map` at specified positions. This method is not concurrency-safe.|  
  
### Public Operators  
  
|Name|Description|  
|----------|-----------------|  
|[concurrent_unordered_map::operator[] Operator](#concurrent_unordered_map__operator_at_operator)|Overloaded. Finds or inserts an element with the specified key. This method is concurrency-safe.|  
|[concurrent_unordered_map::operator= Operator](#concurrent_unordered_map__operator_eq_operator)|Overloaded. Assigns the contents of another `concurrent_unordered_map` object to this one. This method is not concurrency-safe.|  
  
## Remarks  
 For detailed information on the `concurrent_unordered_map` class, see [Parallel Containers and Objects](../VS_visualcpp/Parallel-Containers-and-Objects.md).  
  
## Inheritance Hierarchy  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_map`  
  
## Requirements  
 **Header:** concurrent_unordered_map.h  
  
 **Namespace:** concurrency  
  
##  <a name="concurrent_unordered_map__at_method"></a>  concurrent_unordered_map::at Method  
 Finds an element in a `concurrent_unordered_map` with a specified key value.. This method is concurrency-safe.  
  
```  
mapped_type& at(  
    const key_type& _Keyval );  
  
const mapped_type& at(  
    const key_type& _Keyval ) const;  
```  
  
### Parameters  
 `_Keyval`  
 The key value to find.  
  
### Return Value  
 A reference to the data value of the element found.  
  
### Remarks  
 If the argument key value is not found, the function throws an object of class `out_of_range`.  
  
##  <a name="concurrent_unordered_map__begin_method"></a>  concurrent_unordered_map::begin Method  
 Returns an iterator pointing to the first element in the concurrent container. This method is concurrency safe.  
  
```  
iterator begin();  
  
const_iterator begin() const;  
```  
  
### Return Value  
 An iterator to the first element in the concurrent container.  
  
##  <a name="concurrent_unordered_map__cbegin_method"></a>  concurrent_unordered_map::cbegin Method  
 Returns a const iterator pointing to the first element in the concurrent container. This method is concurrency safe.  
  
```  
const_iterator cbegin() const;  
```  
  
### Return Value  
 A const iterator to the first element in the concurrent container.  
  
##  <a name="concurrent_unordered_map__cend_method"></a>  concurrent_unordered_map::cend Method  
 Returns a const iterator pointing to the location succeeding the last element in the concurrent container. This method is concurrency safe.  
  
```  
const_iterator cend() const;  
```  
  
### Return Value  
 A const iterator to the location succeeding the last element in the concurrent container.  
  
##  <a name="concurrent_unordered_map__clear_method"></a>  concurrent_unordered_map::clear Method  
 Erases all the elements in the concurrent container. This function is not concurrency safe.  
  
```  
void clear();  
```  
  
##  <a name="concurrent_unordered_map__concurrent_unordered_map_constructor"></a>  concurrent_unordered_map::concurrent_unordered_map Constructor  
 Constructs a concurrent unordered map.  
  
```  
explicit concurrent_unordered_map(  
    size_type _Number_of_buckets = 8,  
    const hasher& _Hasher = hasher(),  
    const key_equal& _Key_equality = key_equal(),  
    const allocator_type& _Allocator = allocator_type());  
  
concurrent_unordered_map(  
    const allocator_type& _Allocator );  
  
template <  
    typename _Iterator  
>  
concurrent_unordered_map( _Iterator _Begin, _Iterator _End,  
    size_type _Number_of_buckets = 8,  
    const hasher& _Hasher = hasher(),  
    const key_equal& _Key_equality = key_equal(),  
    const allocator_type& _Allocator = allocator_type());  
  
concurrent_unordered_map(  
    const concurrent_unordered_map& _Umap );  
  
concurrent_unordered_map(  
    const concurrent_unordered_map& _Umap,  
    const allocator_type& _Allocator );  
  
concurrent_unordered_map(  
    concurrent_unordered_map&& _Umap );  
```  
  
### Parameters  
 `_Iterator`  
 The type of the input iterator.  
  
 `_Number_of_buckets`  
 The initial number of buckets for this unordered map.  
  
 `_Hasher`  
 The hash function for this unordered map.  
  
 `_Key_equality`  
 The equality comparison function for this unordered map.  
  
 `_Allocator`  
 The allocator for this unordered map.  
  
 `_Begin`  
 The position of the first element in the range of elements to be copied.  
  
 `_End`  
 The position of the first element beyond the range of elements to be copied.  
  
 `_Umap`  
 The source `concurrent_unordered_map` object to copy or move elements from.  
  
### Remarks  
 All constructors store an allocator object `_Allocator` and initialize the unordered map.  
  
 The first constructor specifies an empty initial map and explicitly specifies the number of buckets, hash function, equality function and allocator type to be used.  
  
 The second constructor specifies an allocator for the unordered map.  
  
 The third constructor specifies values supplied by the iterator range [ `_Begin`, `_End`).  
  
 The fourth and fifth constructors specify a copy of the concurrent unordered map `_Umap`.  
  
 The last constructor specifies a move of the concurrent unordered map `_Umap`.  
  
##  <a name="concurrent_unordered_map__count_method"></a>  concurrent_unordered_map::count Method  
 Counts the number of elements matching a specified key. This function is concurrency safe.  
  
```  
size_type count(    const key_type& _Keyval ) const;  
```  
  
### Parameters  
 `_Keyval`  
 The key to search for.  
  
### Return Value  
 The number of times number of times the key appears in the container.  
  
##  <a name="concurrent_unordered_map__empty_method"></a>  concurrent_unordered_map::empty Method  
 Tests whether no elements are present. This method is concurrency safe.  
  
```  
bool empty() const;  
```  
  
### Return Value  
 `true` if the concurrent container is empty, `false` otherwise.  
  
### Remarks  
 In the presence of concurrent inserts, whether or not the concurrent container is empty may change immediately after calling this function, before the return value is even read.  
  
##  <a name="concurrent_unordered_map__end_method"></a>  concurrent_unordered_map::end Method  
 Returns an iterator pointing to the location succeeding the last element in the concurrent container. This method is concurrency safe.  
  
```  
iterator end();  
  
const_iterator end() const;  
```  
  
### Return Value  
 An iterator to the location succeeding the last element in the concurrent container.  
  
##  <a name="concurrent_unordered_map__equal_range_method"></a>  concurrent_unordered_map::equal_range Method  
 Finds a range that matches a specified key. This function is concurrency safe.  
  
```  
std::pair<iterator, iterator> equal_range(  
    const key_type& _Keyval);  
  
std::pair<const_iterator, const_iterator> equal_range(  
    const key_type& _Keyval ) const;  
```  
  
### Parameters  
 `_Keyval`  
 The key value to search for.  
  
### Return Value  
 A [pair](assetId:///c5a37023-d939-4eb2-ae24-ce8e0cd4505d) where the first element is an iterator to the beginning and the second element is an iterator to the end of the range.  
  
### Remarks  
 It is possible for concurrent inserts to cause additional keys to be inserted after the begin iterator and before the end iterator.  
  
##  <a name="concurrent_unordered_map__find_method"></a>  concurrent_unordered_map::find Method  
 Finds an element that matches a specified key. This function is concurrency safe.  
  
```  
iterator find(  
    const key_type& _Keyval );  
  
const_iterator find(  
    const key_type& _Keyval ) const;  
```  
  
### Parameters  
 `_Keyval`  
 The key value to search for.  
  
### Return Value  
 An iterator pointing to the location of the the first element that matched the key provided, or the iterator `end()` if no such element exists.  
  
##  <a name="concurrent_unordered_map__get_allocator_method"></a>  concurrent_unordered_map::get_allocator Method  
 Returns the stored allocator object for this concurrent container. This method is concurrency safe.  
  
```  
allocator_type get_allocator() const;  
```  
  
### Return Value  
 The stored allocator object for this concurrent container.  
  
##  <a name="concurrent_unordered_map__hash_function_method"></a>  concurrent_unordered_map::hash_function Method  
 Gets the stored hash function object.  
  
```  
hasher hash_function() const;  
```  
  
### Return Value  
 The stored hash function object.  
  
##  <a name="concurrent_unordered_map__insert_method"></a>  concurrent_unordered_map::insert Method  
 Adds elements to the `concurrent_unordered_map` object.  
  
```  
std::pair<iterator, bool> insert(  
    const value_type& _Value );  
  
iterator insert(  
    const_iterator _Where,  
    const value_type& _Value );  
  
template<  
    class _Iterator  
>  
void insert( _Iterator _First, _Iterator _Last );  
  
template<  
    class _Valty  
>  
std::pair<iterator, bool> insert(  
    _Valty&& _Value );  
  
template<  
    class _Valty  
>  
typename std::tr1::enable_if<!std::tr1::is_same<const_iterator, typename std::tr1::remove_reference< _Valty>::type>::value, iterator>::type insert(  
    const_iterator _Where,  
    _Valty&& _Value );  
```  
  
### Parameters  
 `_Iterator`  
 The iterator type used for insertion.  
  
 `_Valty`  
 The type of the value inserted into the map.  
  
 `_Value`  
 The value to be inserted.  
  
 `_Where`  
 The starting location to search for an insertion point.  
  
 `_First`  
 The beginning of the range to insert.  
  
 `_Last`  
 The end of the range to insert.  
  
### Return Value  
 A pair that contains an iterator and a boolean value. See the Remarks section for more details.  
  
### Remarks  
 The first member function determines whether an element X exists in the sequence whose key has equivalent ordering to that of `_Value`. If not, it creates such an element X and initializes it with `_Value`. The function then determines the iterator `where` that designates X. If an insertion occurred, the function returns `std::pair(where, true)`. Otherwise, it returns `std::pair(where, false)`.  
  
 The second member function returns insert( `_Value`), using `_Where` as a starting place within the controlled sequence to search for the insertion point.  
  
 The third member function inserts the sequence of element values from the range [ `_First`, `_Last`).  
  
 The last two member functions behave the same as the first two, except that `_Value` is used to construct the inserted value.  
  
##  <a name="concurrent_unordered_map__key_eq_method"></a>  concurrent_unordered_map::key_eq Method  
 Gets the stored equality comparison function object.  
  
```  
key_equal key_eq() const;  
```  
  
### Return Value  
 The stored equality comparison function object.  
  
##  <a name="concurrent_unordered_map__load_factor_method"></a>  concurrent_unordered_map::load_factor Method  
 Computes and returns the current load factor of the container. The load factor is the number of elements in the container divided by the number of buckets.  
  
```  
float load_factor() const;  
```  
  
### Return Value  
 The load factor for the container.  
  
##  <a name="concurrent_unordered_map__max_load_factor_method"></a>  concurrent_unordered_map::max_load_factor Method  
 Gets or sets the maximum load factor of the container. The maximum load factor is the largest number of elements than can be in any bucket before the container grows its internal table.  
  
```  
float max_load_factor() const;  
void max_load_factor(  
    float _Newmax );  
```  
  
### Parameters  
 `_Newmax`  
  
### Return Value  
 The first member function returns the stored maximum load factor. The second member function does not return a value but throws an [out_of_range](../VS_visualcpp/out_of_range-Class.md) exception if the supplied load factor is invalid..  
  
##  <a name="concurrent_unordered_map__max_size_method"></a>  concurrent_unordered_map::max_size Method  
 Returns the maximum size of the concurrent container, determined by the allocator. This method is concurrency safe.  
  
```  
size_type max_size() const;  
```  
  
### Return Value  
 The maximum number of elements that can be inserted into this concurrent container.  
  
### Remarks  
 This upper bound value may actually be higher than what the container can actually hold.  
  
##  <a name="concurrent_unordered_map__operator_at_operator"></a>  concurrent_unordered_map::operator[] Operator  
 Finds or inserts an element with the specified key. This method is concurrency-safe.  
  
```  
mapped_type&   operator[](const key_type& _Keyval);  
  
mapped_type&   operator[](key_type && _Keyval);  
```  
  
### Parameters  
 `_Keyval`  
 The key value to  
  
 find or insert.  
  
### Return Value  
 A reference to the data value of the found or inserted element.  
  
### Remarks  
 If the argument key value is not found, then it is inserted along with the default value of the data type.  
  
 `operator[]` may be used to insert elements into a map `m` using `m[_Key] = DataValue;`, where `DataValue` is the value of the `mapped_type` of the element with a key value of `_Key`.  
  
 When using `operator[]` to insert elements, the returned reference does not indicate whether an insertion is changing a pre-existing element or creating a new one. The member functions `find` and [insert](#concurrent_unordered_map__insert_method) can be used to determine whether an element with a specified key is already present before an insertion.  
  
##  <a name="concurrent_unordered_map__operator_eq_operator"></a>  concurrent_unordered_map::operator= Operator  
 Assigns the contents of another `concurrent_unordered_map` object to this one. This method is not concurrency-safe.  
  
```  
concurrent_unordered_map&  operator= (  
    const concurrent_unordered_map& _Umap );  
  
concurrent_unordered_map&  operator= (  
    concurrent_unordered_map&& _Umap );  
```  
  
### Parameters  
 `_Umap`  
 The source `concurrent_unordered_map` object.  
  
### Return Value  
 A reference to this `concurrent_unordered_map` object.  
  
### Remarks  
 After erasing any existing elements a concurrent vector, `operator=` either copies or moves the contents of `_Umap` into the concurrent vector.  
  
##  <a name="concurrent_unordered_map__rehash_method"></a>  concurrent_unordered_map::rehash Method  
 Rebuilds the hash table.  
  
```  
void rehash(    size_type _Buckets );  
```  
  
### Parameters  
 `_Buckets`  
 The desired number of buckets.  
  
### Remarks  
 The member function alters the number of buckets to be at least `_Buckets` and rebuilds the hash table as needed. The number of buckets must be a power of 2. If not a power of 2, it will be rounded up to the next largest power of 2.  
  
 It throws an [out_of_range](../VS_visualcpp/out_of_range-Class.md) exception if the number of buckets is invalid (either 0 or greater than the maximum number of buckets).  
  
##  <a name="concurrent_unordered_map__size_method"></a>  concurrent_unordered_map::size Method  
 Returns the number of elements in this concurrent container. This method is concurrency safe.  
  
```  
size_type size() const;  
```  
  
### Return Value  
 The number of items in the container.  
  
### Remarks  
 In the presence of concurrent inserts, the number of elements in the concurrent container may change immediately after calling this function, before the return value is even read.  
  
##  <a name="concurrent_unordered_map__swap_method"></a>  concurrent_unordered_map::swap Method  
 Swaps the contents of two `concurrent_unordered_map` objects. This method is not concurrency-safe.  
  
```  
void swap(    concurrent_unordered_map& _Umap );  
```  
  
### Parameters  
 `_Umap`  
 The `concurrent_unordered_map` object to swap with.  
  
##  <a name="concurrent_unordered_map__unsafe_begin_method"></a>  concurrent_unordered_map::unsafe_begin Method  
 Returns an iterator to the first element in this container for a specific bucket.  
  
```  
local_iterator unsafe_begin(  
    size_type _Bucket );  
  
const_local_iterator unsafe_begin(  
    size_type _Bucket ) const;  
```  
  
### Parameters  
 `_Bucket`  
 The bucket index.  
  
### Return Value  
 An iterator pointing to the beginning of the bucket.  
  
##  <a name="concurrent_unordered_map__unsafe_bucket_method"></a>  concurrent_unordered_map::unsafe_bucket Method  
 Returns the bucket index that a specific key maps to in this container.  
  
```  
size_type unsafe_bucket(    const key_type& _Keyval ) const;  
```  
  
### Parameters  
 `_Keyval`  
 The element key being searched for.  
  
### Return Value  
 The bucket index for the key in this container.  
  
##  <a name="concurrent_unordered_map__unsafe_bucket_count_method"></a>  concurrent_unordered_map::unsafe_bucket_count Method  
 Returns the current number of buckets in this container.  
  
```  
size_type unsafe_bucket_count() const;  
```  
  
### Return Value  
 The current number of buckets in this container.  
  
##  <a name="concurrent_unordered_map__unsafe_bucket_size_method"></a>  concurrent_unordered_map::unsafe_bucket_size Method  
 Returns the number of items in a specific bucket of this container.  
  
```  
size_type unsafe_bucket_size(    size_type _Bucket );  
```  
  
### Parameters  
 `_Bucket`  
 The bucket to search for.  
  
### Return Value  
 The current number of buckets in this container.  
  
##  <a name="concurrent_unordered_map__unsafe_cbegin_method"></a>  concurrent_unordered_map::unsafe_cbegin Method  
 Returns an iterator to the first element in this container for a specific bucket.  
  
```  
const_local_iterator unsafe_cbegin(    size_type _Bucket ) const;  
```  
  
### Parameters  
 `_Bucket`  
 The bucket index.  
  
### Return Value  
 An iterator pointing to the beginning of the bucket.  
  
##  <a name="concurrent_unordered_map__unsafe_cend_method"></a>  concurrent_unordered_map::unsafe_cend Method  
 Returns an iterator to the location succeeding the last element in a specific bucket.  
  
```  
const_local_iterator unsafe_cend( size_type _Bucket ) const;  
```  
  
### Parameters  
 `_Bucket`  
 The bucket index.  
  
### Return Value  
 An iterator pointing to the beginning of the bucket.  
  
##  <a name="concurrent_unordered_map__unsafe_end_method"></a>  concurrent_unordered_map::unsafe_end Method  
 Returns an iterator to the last element in this container for a specific bucket.  
  
```  
local_iterator unsafe_end(  
    size_type _Bucket );  
  
const_local_iterator unsafe_end(  
    size_type _Bucket ) const;  
```  
  
### Parameters  
 `_Bucket`  
 The bucket index.  
  
### Return Value  
 An iterator pointing to the end of the bucket.  
  
##  <a name="concurrent_unordered_map__unsafe_erase_method"></a>  concurrent_unordered_map::unsafe_erase Method  
 Removes elements from the `concurrent_unordered_map` at specified positions. This method is not concurrency-safe.  
  
```  
iterator unsafe_erase(  
    const_iterator _Where );  
  
iterator unsafe_erase(  
    const_iterator _Begin,  
    const_iterator _End );  
  
size_type unsafe_erase(  
    const key_type& _Keyval );  
```  
  
### Parameters  
 `_Where`  
 The iterator position to erase from.  
  
 `_Begin`  
 The position of the first element in the range of elements to be erased.  
  
 `_End`  
 The position of the first element beyond the range of elements to be erased.  
  
 `_Keyval`  
 The key value to erase.  
  
### Return Value  
 The first two member functions return an iterator that designates the first element remaining beyond any elements removed, or `concurrent_unordered_map::end`() if no such element exists. The third member function returns the number of elements it removes.  
  
### Remarks  
 The first member function removes the element of the controlled sequence pointed to by `_Where`. The second member function removes the elements in the range [ `_Begin`, `_End`).  
  
 The third member function removes the elements in the range delimited by `concurrent_unordered_map::equal_range`(_Keyval).  
  
##  <a name="concurrent_unordered_map__unsafe_max_bucket_count_method"></a>  concurrent_unordered_map::unsafe_max_bucket_count Method  
 Returns the maximum number of buckets in this container.  
  
```  
size_type unsafe_max_bucket_count() const;  
```  
  
### Return Value  
 The maximum number of buckets in this container.  
  
## See Also  
 [concurrency Namespace](../VS_visualcpp/concurrency-Namespace.md)   
 [Parallel Containers and Objects](../VS_visualcpp/Parallel-Containers-and-Objects.md)