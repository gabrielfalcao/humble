# humble
> Version 0.4.0

# What

a library for expressive BDD tests on python

# Install

    user@machine:~$ [sudo] pip install humble

# Documentation

    from humble import describe

    from mymodule import User

    # objects
    john = User(name="John Doe")

    he = describe(john, as_a="User")
    he.should_be_a(User)
    he.should_have("name").identical_to("John Doe")

    # lists

    my_list = ['banana', 'apple']

    it = describe(my_list, as_a='list of fruits')
    it.should_be.iterable
    it.has_the_member("banana")

    it.should_have.strings_only
    it.should_have(2).members


    it = describe([], as_a="empty_list")
    it.should_be.iterable
    it.should_be.empty


    # dicts

    my_dict = {'name': 'Testy McTesterson'}
    it = describe(my_dict, as_a="User")
    it.should_be_a(dict)
    it.should_be.iterable
    it.has_the_member("name")
    it.should_have("name").identical_to('Testy McTesterson')

    it.should_have("name").similar_to('')
