# Events & Data

## Type of events:

* [#submission.commented](events-and-data.md#submission.commented "mention")
* [#comment.replied](events-and-data.md#comment.replied "mention")
* [#application.submitted](events-and-data.md#application.submitted "mention")
* [#submission.status.updated](events-and-data.md#submission.status.updated "mention")

***

{% hint style="info" %}
When someone replies to a comment, the event 'comment.replied' is fired instead of 'submission.commented'
{% endhint %}

### submission.commented

{% code fullWidth="false" %}
```typescript
{
    event: 'application.commented'
    project: {
        id: string;
        name: string;
        slug: string;
        language: string;
        iconUrl: string;
    };
    comment: {
        id: string;
        content: string;
        user: {
            id: string;
            displayName: string;
            name: string;
            avatarUrl: string;
            loginProvidersIds: {
                DISCORD: string;
            }
        },
        createdAt: Date;
    },
    submission: {
        id: string;
        user: {
            id: string;
            displayName: string;
            name: string;
            avatarUrl: string;
            loginProvidersIds: {
                DISCORD: string;
            }
        },
        form: {
            id: string;
            name: string;
            slug: string;
        },
        createdAt: Date;
    }
}
```
{% endcode %}

### comment.replied

```typescript
{
    event: 'application.replied'
    project: {
        id: string;
        name: string;
        slug: string;
        language: string;
        iconUrl: string;
    };
    comment: {
        id: string;
        content: string;
        user: {
            id: string;
            displayName: string;
            name: string;
            avatarUrl: string;
            loginProvidersIds: {
                DISCORD: string;
            }
        },
        parentComment: {
            id: string;
            content: string;
            user: {
                id: string;
                displayName: string;
                name: string;
                avatarUrl: string;
                loginProvidersIds: {
                    DISCORD: string;
                }
            },
            createdAt: Date;
        },
        createdAt: Date;
    },
    submission: {
        id: string;
        status: 'PENDING' | 'REJECTED' | 'APPROVED',
        user: {
            id: string;
            displayName: string;
            name: string;
            avatarUrl: string;
            loginProvidersIds: {
                DISCORD: string;
            }
        },
        form: {
            id: string;
            title: string;
            slug: string;
        },
        createdAt: Date;
    }
}
```

### application.submitted

```typescript
{
    event: 'application.submitted'
    project: {
        id: string;
        name: string;
        slug: string;
        language: string;
        iconUrl: string;
    }
    submission: {
        id: string;
        form: {
            id: string;
            title: string;
            slug: string;
        };
        answers: {
            fieldId: string;
            fieldName: string;
            value: string;
        }[];
        createdAt: Date;
    }
    user: {
        id: string;
        displayName: string;
        name: string;
        avatarUrl: string;
        loginProvidersIds: {
            DISCORD: string;
        }
    }

}
```

### submission.status.updated

```typescript
{
    event: 'submission.status.updated'    
    project: {
        id: string;
        name: string;
        slug: string;
        language: string;
        iconUrl: string;
    }
    submission: {
        id: string;
        status: 'PENDING' | 'REJECTED' | 'APPROVED',
        form: {
            id: string;
            title: string;
            slug: string;
        }
        user: {
            id: string;
            displayName: string;
            name: string;
            avatarUrl: string;
            loginProvidersIds: {
                DISCORD: string;
            }
        }
        createdAt: Date;
    }
}
```
