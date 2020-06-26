# Ideas and Guidelines for `numpy-handbook`

## Target Audience

 - There are a ton of great NumPy resources already out there, to say nothing
   of the new tutorials that will be developed in conjunction with the NEP 44
   efforts (and projects like the GSoD). In order for this book to be truly
   worth it, `numpy-handbook` must address things from a perspective that is
   not already well-covered by existing literature/tutorials. 

 - Primarily target *existing users* with content aimed at improving 
   proficiency of those who are already familiar with NumPy.
   * I really like the concept of something analogous to [Fluent Python][fp]
     for NumPy. Fluent Python uses a variety of examples to help the reader
     develop a complete, thorough understanding of the Python data model.
     IMO this is an extremely effective approach and I'd like to attempt 
     something similar for the `ndarray` data model.
   * Fluent Python targets Python users who don't necessarily have a complete
     understanding of the data model and thus might not be using all the
     language features to their fullest extent. I think this maps very nicely
     to the target audience for a `numpy-handbook`.
   * FP also covers a lot of the same material as the Python reference docs;
     but what makes it so compelling (IMO) is the illustrative/example-driven
     nature of the material.

 - The NumPy documentation (especially the user-facing docs) have components
   that are targeted for converts from Matlab. This is an important angle,
   but with the reach of the scientific Python ecosystem, there are probably a
   lot of new users coming from technique or application-specific domains that
   are using NumPy "by default" since `ndarray` is a core component of the 
   whole ecosystem. It would be good to highlight/generate content geared 
   towards these types of users.

## Example-driven

 - Lean into *learn-by-doing* philosophy, especially when it comes to 
   increasing user comfort level with the `ndarray` model.
 - Have an eye towards making it easy for users to contribute examples. This
   includes many ideas that are relevant for the documentation (particularly
   tutorials) as well:
     * Provide a tagging mechanism to label examples with keywords
     * Keep metadata on which features a particular example is intended to 
       highlight so that different examples (e.g. from a different domain) 
       could be included instead.


[fp]: https://github.com/fluentpython

## Topics

A scratch area to keep track of some topic ideas, without necessarily 
worrying about how topics will be organized/connected (at this stage)

 - Memory management
   
   Underlies quite a few topics
   
   * From the perspective of **optimzation** strided ops for multi-D arys)
   * nd-index model: linear (i.e. 2-param) mapping from 1D contig. memory
     to *any* n-dim shape
   * C vs. F layout - special attention to greater than 2 dims
     - where 'K' becomes relevant
     - Examples from the perspective of optimization
   * Explain what impact this has on determining when NumPy makes copies
     implicitly
     - Perhaps a separate chapter/section to account for the role that 
       type promotion/coercion plays w/ operations
   
 - Types/promotion
   * Seemingly very common source of confusion (TODO: collate issues from GH)
   * Python scalars vs. NumPy scalars & promotion/casting
     - e.g. Python `int` w/ value > 2**64-1 -> `object` (#16689)
   * Not a NumPy issue, but related - floating point precision
     - How prevalent are these in the issue tracker? If very, perhaps worth
       covering in a subsection (or at least a callout)
       
 - Array creation API
   * e.g. nested, structured dtype (#16678)
     - Gotchas/corner cases. Worth expanding on?
 
 - Relationship between ndarray methods and functions with same name
   - behavior often different; is there a general rule or any guiding
     principles that can help users determine when/why there are 
     differences or is it just a case-by-case situation?
